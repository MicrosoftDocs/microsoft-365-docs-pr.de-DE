---
title: Massenwerte für Reklamations Ebenen, Massenversender, BCL-Ebenen, Funktionsweise von BCL, BCL-Bewertungen, Antispam, Antispam-Header, Massen-e-Mail-Filterung, Massen-e-Mail-Stopp
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Informationen zu BCL-Werten (Bulk Compliance Level) in Office 365.
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030152"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="e2478-103">Massen Reklamations Ebene (BCL) in Office 365</span><span class="sxs-lookup"><span data-stu-id="e2478-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="e2478-104">Massenversender unterscheiden sich in ihren Sende Mustern, der Inhaltserstellung und den Empfänger Akquisitions Methoden.</span><span class="sxs-lookup"><span data-stu-id="e2478-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="e2478-105">Einige sind gute Massen-e-Mails, die gewünschte Nachrichten mit relevanten Inhalten an Ihre Abonnenten senden.</span><span class="sxs-lookup"><span data-stu-id="e2478-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="e2478-106">Diese Nachrichten führen zu wenigen Beschwerden von Empfängern.</span><span class="sxs-lookup"><span data-stu-id="e2478-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="e2478-107">Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.</span><span class="sxs-lookup"><span data-stu-id="e2478-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="e2478-108">Nachrichten von einem Massen-Mailer werden als Massen-oder grau-e-Mail bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2478-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="e2478-109">Um Nachrichten von verschiedenen Typen von Massen-e-Mails zu unterscheiden, wird eingehende e-Mail von Massen-e-Mails an Office 365 (Exchange Online oder eigenständiger Exchange Online Schutz (EoP) ohne Exchange Online Postfächer) eine Massen Reklamations Ebene (BCL) zugewiesen, die zu hinzugefügt wird die Nachricht in einer X-Kopfzeile.</span><span class="sxs-lookup"><span data-stu-id="e2478-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="e2478-110">Die BCL ähnelt der [SCL-Bewertung (Spam Confidence Level)](spam-confidence-levels.md) , die verwendet wird, um Nachrichten als Spam zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e2478-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="e2478-111">Eine höhere BCL gibt an, dass eine Massen Nachricht häufiger Beschwerden generiert (und daher eher Spam ist).</span><span class="sxs-lookup"><span data-stu-id="e2478-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e2478-112">Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-e-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e2478-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="e2478-113">Bei der Spam Filterung werden Nachrichten als **Massen-e-Mails** auf der Grundlage des BCL-Schwellenwerts (der Standardwert oder ein von Ihnen festgelegter Wert) markiert und die angegebene Aktion für die Nachricht verwendet (die Standardaktion lautet "Nachricht an den Junk-e-Mail-Ordner des Empfängers senden"</span><span class="sxs-lookup"><span data-stu-id="e2478-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="e2478-114">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md) und [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="e2478-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="e2478-115">Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2478-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="e2478-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="e2478-116">**BCL**</span></span>|<span data-ttu-id="e2478-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e2478-117">**Description**</span></span>|
|<span data-ttu-id="e2478-118">0</span><span class="sxs-lookup"><span data-stu-id="e2478-118">0</span></span>|<span data-ttu-id="e2478-119">Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.</span><span class="sxs-lookup"><span data-stu-id="e2478-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="e2478-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="e2478-120">1, 2, 3</span></span>|<span data-ttu-id="e2478-121">Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="e2478-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="e2478-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="e2478-122">4, 5, 6, 7</span></span>|<span data-ttu-id="e2478-123">Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="e2478-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="e2478-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="e2478-124">8, 9</span></span>|<span data-ttu-id="e2478-125">Die Nachricht stammt von einem Massen Absender, der eine hohe Anzahl von Beschwerden generiert.</span><span class="sxs-lookup"><span data-stu-id="e2478-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
