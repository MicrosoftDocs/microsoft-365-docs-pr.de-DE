---
title: SCL-Bewertungen (Spam Confidence Level)
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Wenn eine E-Mail die Spamfilterung passiert, wird ihr eine Spambewertung zugewiesen. Diese Bewertung ist einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet und wird als Stempel im X-Header angezeigt. Der Dienst verfährt mit den Nachrichten entsprechend der Spam Confidence-Interpretation der SCL-Bewertung. In der folgenden Tabelle ist aufgeführt, wie die unterschiedlichen SCL-Bewertungen von den Filtern interpretiert werden, und welche Aktionen standardmäßig für eingehende Nachrichten als Reaktion auf die einzelnen Bewertung erfolgen.
ms.openlocfilehash: 93b3886e1128024f3f7f2a844e2ed603e27d9b2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082643"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="c5730-106">SCL-Bewertungen (Spam Confidence Level)</span><span class="sxs-lookup"><span data-stu-id="c5730-106">Spam confidence levels</span></span>

<span data-ttu-id="c5730-p102">Wenn eine E-Mail die Spamfilterung passiert, wird ihr eine Spambewertung zugewiesen. Diese Bewertung ist einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet und wird als Stempel im X-Header angezeigt. Der Dienst verfährt mit den Nachrichten entsprechend der Spam Confidence-Interpretation der SCL-Bewertung. In der folgenden Tabelle ist aufgeführt, wie die unterschiedlichen SCL-Bewertungen von den Filtern interpretiert werden, und welche Aktionen standardmäßig für eingehende Nachrichten als Reaktion auf die einzelnen Bewertung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c5730-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="c5730-111">**SCL-Bewertung**</span><span class="sxs-lookup"><span data-stu-id="c5730-111">**SCL Rating**</span></span>|<span data-ttu-id="c5730-112">**Spam Confidence-Interpretation**</span><span class="sxs-lookup"><span data-stu-id="c5730-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="c5730-113">**Standardaktion**</span><span class="sxs-lookup"><span data-stu-id="c5730-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5730-114">-1</span><span class="sxs-lookup"><span data-stu-id="c5730-114">-1</span></span>|<span data-ttu-id="c5730-115">Nicht-Spam, der von einem sicheren Absender, einem sicheren Empfänger oder einer sicheren aufgeführten IP-Adresse (vertrauenswürdiger Partner) stammt.</span><span class="sxs-lookup"><span data-stu-id="c5730-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="c5730-116">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="c5730-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c5730-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="c5730-117">0, 1</span></span>|<span data-ttu-id="c5730-118">Nicht-Spam, da die Nachricht überprüft und als bereinigt festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5730-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="c5730-119">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="c5730-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c5730-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="c5730-120">5, 6</span></span>|<span data-ttu-id="c5730-121">Spam</span><span class="sxs-lookup"><span data-stu-id="c5730-121">Spam</span></span>|<span data-ttu-id="c5730-122">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="c5730-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="c5730-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="c5730-123">7, 8, 9</span></span>|<span data-ttu-id="c5730-124">Spam mit hoher Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="c5730-124">High confidence spam</span></span>|<span data-ttu-id="c5730-125">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="c5730-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="c5730-126">SCL-Bewertungen von 2, 3, 4, 7 und 8 werden vom Dienst nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c5730-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="c5730-127">Eine SCL-Bewertung von 5 oder 6 wird als mutmaßlicher Spam betrachtet, der weniger sicher als Spam ist als eine SCL-Bewertung von 9, die als bestimmter Spam betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="c5730-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="c5730-128">Unterschiedliche Aktionen für Spam und Spam mit hoher Vertrauenswürdigkeit können über Ihre Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c5730-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="c5730-129">Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c5730-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="c5730-130">Sie können auch die SCL-Bewertung für Nachrichten festlegen, die bestimmten Bedingungen unter Verwendung von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) entsprechen, wie in [Verwenden von Nachrichtenfluss Regeln beschrieben, um den SCL-Wert (Spam Confidence Level) in Nachrichten festzulegen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c5730-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="c5730-131">Wenn Sie eine e-Mail-Fluss Regel zum Festlegen der SCL-Bewertung von 7, 8 oder 9 verwenden, wird die Nachricht als Spam mit hoher Vertrauenswürdigkeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="c5730-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="c5730-p104">![Das Kurzsymbol für LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Neu bei Office 365?**         Entdecken Sie die kostenlosen Videokurse für **Office 365 admins and IT pros**, präsentiert von LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="c5730-p104">![The short icon for LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

