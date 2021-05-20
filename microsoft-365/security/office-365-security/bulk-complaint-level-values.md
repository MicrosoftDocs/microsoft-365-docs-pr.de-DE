---
title: Massenbeschwerdungsebenenwerte
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratoren können mehr über Massenbeschwerdenebenenwerte (Bulk Complaint Level, BCL) erfahren, die in Exchange Online Protection (EOP) verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537943"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="0b6a6-103">Massenbeschwerdestufe (Bulk Complaint Level, BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="0b6a6-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b6a6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0b6a6-104">**Applies to**</span></span>
- [<span data-ttu-id="0b6a6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b6a6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b6a6-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="0b6a6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0b6a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b6a6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0b6a6-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer weist EOP eingehenden Nachrichten von Massenmailern eine Massenbeschwerdestufe (Bulk Complaint Level, BCL) zu.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="0b6a6-109">Die BCL wird der Nachricht in einem X-Header hinzugefügt und ähnelt der Spam confidence [level (SCL),](spam-confidence-levels.md) die zum Identifizieren von Nachrichten als Spam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="0b6a6-110">Eine höhere BCL gibt an, dass eine Massennachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (und daher eher Spam ist).</span><span class="sxs-lookup"><span data-stu-id="0b6a6-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="0b6a6-111">Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-E-Mails zu identifizieren und die entsprechende BCL zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="0b6a6-112">Massen-E-Mails variieren in ihren Sendemustern, inhaltserstellungs- und Empfängererwerbspraktiken.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="0b6a6-113">Gute Massen-E-Mail-Nachrichten senden gewünschte Nachrichten mit relevanten Inhalten an ihre Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="0b6a6-114">Diese Nachrichten führen zu wenigen Beschwerden von Empfängern.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="0b6a6-115">Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="0b6a6-116">Nachrichten von einem Massen-E-Mail-Nachrichten werden als Massen-E-Mails oder graue E-Mails bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="0b6a6-117">Die Spamfilterung  markiert Nachrichten als Massen-E-Mail basierend auf dem BCL-Schwellenwert (standardwert oder einen von Ihnen angegebenen Wert) und führt die angegebene Aktion für die Nachricht aus (die Standardaktion ist, dass die Nachricht an den Junk-E-Mail-Ordner des Empfängers zugestellt wird).</span><span class="sxs-lookup"><span data-stu-id="0b6a6-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="0b6a6-118">Weitere Informationen finden Sie unter Konfigurieren von Antispamrichtlinien und Was ist der Unterschied zwischen [Junk-E-Mails](configure-your-spam-filter-policies.md) [und Massen-E-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="0b6a6-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="0b6a6-119">Sie können die Mandanten zulassen/blockieren-Liste verwenden, um Ausnahmen für die Massen-E-Mail-Filterung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="0b6a6-120">Nachrichten von Absendern in den angegebenen Domänen  erhalten die Aktion für das Spamfilter-Urteil Massen-E-Mails in Antispamrichtlinien nicht.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="0b6a6-121">Weitere Informationen finden Sie [unter Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span><span class="sxs-lookup"><span data-stu-id="0b6a6-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="0b6a6-122">Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="0b6a6-123">BCL</span><span class="sxs-lookup"><span data-stu-id="0b6a6-123">BCL</span></span>|<span data-ttu-id="0b6a6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b6a6-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="0b6a6-125">0</span><span class="sxs-lookup"><span data-stu-id="0b6a6-125">0</span></span>|<span data-ttu-id="0b6a6-126">Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="0b6a6-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="0b6a6-127">1, 2, 3</span></span>|<span data-ttu-id="0b6a6-128">Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="0b6a6-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b6a6-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="0b6a6-130">Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="0b6a6-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="0b6a6-131">8, 9</span></span>|<span data-ttu-id="0b6a6-132">Die Nachricht stammt von einem Massensender, der eine hohe Anzahl von Beschwerden generiert.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="0b6a6-133"><sup>\*</sup> Dies ist der Standardwert, der in Antispamrichtlinien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b6a6-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
