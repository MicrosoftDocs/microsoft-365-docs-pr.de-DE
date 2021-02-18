---
title: Werte der Ebene für Massenbeanstandung
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
description: Administratoren können sich über Werte der Massenkonformitätsstufe (Bulk Compliance Level, BCL) informieren, die in Exchange Online Protection (EOP) verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289895"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="b8af7-103">BCL (Bulk Complaint Level) in EOP</span><span class="sxs-lookup"><span data-stu-id="b8af7-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b8af7-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="b8af7-104">**Applies to**</span></span>
- [<span data-ttu-id="b8af7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b8af7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b8af7-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="b8af7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b8af7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8af7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b8af7-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer weist EOP eingehenden Nachrichten von Massen-E-Mail-Benutzern eine massenkonforme Ebene (BCL) zu.</span><span class="sxs-lookup"><span data-stu-id="b8af7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="b8af7-109">Der BCL wird der Nachricht in einem X-Header hinzugefügt und ähnelt dem [SCL (Spam Confidence Level),](spam-confidence-levels.md) mit dem Nachrichten als Spam identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="b8af7-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="b8af7-110">Ein höherer BCL gibt an, dass eine Massennachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (und daher mit höherer Wahrscheinlichkeit Spam ist).</span><span class="sxs-lookup"><span data-stu-id="b8af7-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="b8af7-111">Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-E-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b8af7-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="b8af7-112">Massen-E-Mail-Absender variieren in ihren Sendemustern, Inhaltserstellungs- und Empfängererwerbsmethoden.</span><span class="sxs-lookup"><span data-stu-id="b8af7-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="b8af7-113">Gute Massen-E-Mail-Nachrichten senden die gewünschten Nachrichten mit relevanten Inhalten an ihre Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="b8af7-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="b8af7-114">Diese Nachrichten führen zu wenigen Beschwerden von Empfängern.</span><span class="sxs-lookup"><span data-stu-id="b8af7-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="b8af7-115">Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.</span><span class="sxs-lookup"><span data-stu-id="b8af7-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="b8af7-116">Nachrichten von einem Massen-E-Mail-Nachrichten werden als Massen-E-Mails oder graue E-Mails bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b8af7-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="b8af7-117">Die Spamfilterung  markiert Nachrichten als Massen-E-Mail basierend auf dem BCL-Schwellenwert (standardwert oder einem von Ihnen angegebenen Wert) und führt die angegebene Aktion für die Nachricht aus (die Standardaktion besteht in der Bereitstellung der Nachricht an den Junk-E-Mail-Ordner des Empfängers).</span><span class="sxs-lookup"><span data-stu-id="b8af7-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="b8af7-118">Weitere Informationen finden Sie unter ["Konfigurieren von Antispamrichtlinien"](configure-your-spam-filter-policies.md) und was [ist der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="b8af7-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="b8af7-119">Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8af7-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="b8af7-120">BCL</span><span class="sxs-lookup"><span data-stu-id="b8af7-120">BCL</span></span>|<span data-ttu-id="b8af7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8af7-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="b8af7-122">0</span><span class="sxs-lookup"><span data-stu-id="b8af7-122">0</span></span>|<span data-ttu-id="b8af7-123">Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.</span><span class="sxs-lookup"><span data-stu-id="b8af7-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="b8af7-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="b8af7-124">1, 2, 3</span></span>|<span data-ttu-id="b8af7-125">Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="b8af7-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="b8af7-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b8af7-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="b8af7-127">Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="b8af7-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="b8af7-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="b8af7-128">8, 9</span></span>|<span data-ttu-id="b8af7-129">Die Nachricht stammt von einem Massensender, der eine hohe Anzahl von Beschwerden generiert.</span><span class="sxs-lookup"><span data-stu-id="b8af7-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="b8af7-130"><sup>\*</sup> Dies ist der Standardschwellenwert, der in Antispamrichtlinien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8af7-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
