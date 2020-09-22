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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die SCL-Bewertung (Spam Confidence Level) informieren, die auf Nachrichten in Exchange Online Protection (EoP) angewendet wird.
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202233"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="42d62-103">SCL (Spam Confidence Level) in EoP</span><span class="sxs-lookup"><span data-stu-id="42d62-103">Spam confidence level (SCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="42d62-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden eingehende Nachrichten über die Spamfilterung in EoP durchlaufen und einem Spam-Faktor zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="42d62-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="42d62-105">Das Ergebnis wird einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet, die der Nachricht in einer X-Kopfzeile hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="42d62-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="42d62-106">Eine höhere SCL-Bewertung gibt an, dass eine Nachricht eher Spam ist.</span><span class="sxs-lookup"><span data-stu-id="42d62-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="42d62-107">EoP nimmt auf der Nachricht basierend auf der SCL-Bewertung Aktionen vor.</span><span class="sxs-lookup"><span data-stu-id="42d62-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="42d62-108">Was der SCL-Wert bedeutet und welche Standardaktionen für Nachrichten ausgeführt werden, wird in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42d62-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="42d62-109">Weitere Informationen zu Aktionen, die Sie Nachrichten basierend auf dem Spamfilter Urteil ausführen können, finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="42d62-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="42d62-110">SCL</span><span class="sxs-lookup"><span data-stu-id="42d62-110">SCL</span></span>|<span data-ttu-id="42d62-111">Definition</span><span class="sxs-lookup"><span data-stu-id="42d62-111">Definition</span></span>|<span data-ttu-id="42d62-112">Standardaktion</span><span class="sxs-lookup"><span data-stu-id="42d62-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="42d62-113">-1</span><span class="sxs-lookup"><span data-stu-id="42d62-113">-1</span></span>|<span data-ttu-id="42d62-114">Die Nachricht hat die Spamfilterung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="42d62-114">The message skipped spam filtering.</span></span> <span data-ttu-id="42d62-115">Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem e-Mail-Quellserver in der IP-Zulassungsliste.</span><span class="sxs-lookup"><span data-stu-id="42d62-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="42d62-116">Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten in EoP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="42d62-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="42d62-117">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="42d62-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="42d62-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="42d62-118">0, 1</span></span>|<span data-ttu-id="42d62-119">Spamfilterung bestimmt, dass die Nachricht kein Spam war.</span><span class="sxs-lookup"><span data-stu-id="42d62-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="42d62-120">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="42d62-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="42d62-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="42d62-121">5, 6</span></span>|<span data-ttu-id="42d62-122">Spamfilterung markiert die Nachricht als **Spam**</span><span class="sxs-lookup"><span data-stu-id="42d62-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="42d62-123">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="42d62-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="42d62-124">9 </span><span class="sxs-lookup"><span data-stu-id="42d62-124">9</span></span>|<span data-ttu-id="42d62-125">Spamfilterung kennzeichnete die Nachricht als **Spam mit hoher Vertrauens** Würdigkeit</span><span class="sxs-lookup"><span data-stu-id="42d62-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="42d62-126">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="42d62-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="42d62-127">Sie werden feststellen, dass die SCL-Bewertung 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42d62-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="42d62-128">Mithilfe von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) können Sie die SCL-Bewertung für Nachrichten Stempeln.</span><span class="sxs-lookup"><span data-stu-id="42d62-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="42d62-129">Wenn Sie eine e-Mail-Fluss Regel zum Festlegen der SCL-Bewertung verwenden, lösen die Werte 5 oder 6 die Spam Filterungs Aktion für **Spam**aus, und die Werte 7, 8 oder 9 lösen die Spam Filterungs Aktion für **Spam mit hoher Vertrauens**Würdigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="42d62-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="42d62-130">Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="42d62-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="42d62-131">Ähnlich wie bei der SCL-Bewertung identifiziert die Massen Reklamations Stufe (BCL) ungültige Massen-e-Mails (auch als _graue e-Mail_bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="42d62-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="42d62-132">Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist).</span><span class="sxs-lookup"><span data-stu-id="42d62-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="42d62-133">Sie konfigurieren den BCL-Schwellenwert in Anti-Spam-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="42d62-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="42d62-134">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md), [Bulk Complaint Level (BCL) in EoP)](bulk-complaint-level-values.md)und [worin besteht der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="42d62-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="42d62-135">![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="42d62-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="42d62-136">Entdecken Sie ﻿kostenlose Video Kurse für **Microsoft 365-Administratoren und IT-Experten**, die Ihnen von LinkedIn Learning angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="42d62-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
