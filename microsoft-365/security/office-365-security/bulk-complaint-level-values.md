---
title: Werte für Massen Reklamations Stufen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den Werten für die Massen Konformitätsstufe (BCL) erhalten, die in Exchange Online Protection (EoP) verwendet werden.
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209607"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="06f86-103">Massen Reklamations Ebene (BCL) in EoP</span><span class="sxs-lookup"><span data-stu-id="06f86-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="06f86-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer weist EoP eingehenden Nachrichten von Massen versandern eine Massen konforme Ebene (BCL) zu.</span><span class="sxs-lookup"><span data-stu-id="06f86-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="06f86-105">Die BCL wird der Nachricht in einer X-Kopfzeile hinzugefügt und ähnelt der [SCL-Bewertung (Spam Confidence Level)](spam-confidence-levels.md) , die zum Identifizieren von Nachrichten als Spam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06f86-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="06f86-106">Eine höhere BCL gibt an, dass eine Massen Nachricht häufiger Beschwerden generiert (und daher eher Spam ist).</span><span class="sxs-lookup"><span data-stu-id="06f86-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="06f86-107">Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-e-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="06f86-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="06f86-108">Massenversender unterscheiden sich in ihren Sende Mustern, der Inhaltserstellung und den Empfänger Akquisitions Methoden.</span><span class="sxs-lookup"><span data-stu-id="06f86-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="06f86-109">Gute Massenversender senden gewünschte Nachrichten mit relevanten Inhalten an Ihre Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="06f86-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="06f86-110">Diese Nachrichten führen zu wenigen Beschwerden von Empfängern.</span><span class="sxs-lookup"><span data-stu-id="06f86-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="06f86-111">Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.</span><span class="sxs-lookup"><span data-stu-id="06f86-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="06f86-112">Nachrichten von einem Massen-Mailer werden als Massen-oder grau-e-Mail bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="06f86-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="06f86-113">Bei der Spam Filterung werden Nachrichten als **Massen-e-Mails** auf der Grundlage des BCL-Schwellenwerts (der Standardwert oder ein von Ihnen festgelegter Wert) markiert und die angegebene Aktion für die Nachricht verwendet (die Standardaktion lautet "Nachricht an den Junk-e-Mail-Ordner des Empfängers senden"</span><span class="sxs-lookup"><span data-stu-id="06f86-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="06f86-114">Weitere Informationen finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md) und [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="06f86-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="06f86-115">Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06f86-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="06f86-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="06f86-116">**BCL**</span></span>|<span data-ttu-id="06f86-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="06f86-117">**Description**</span></span>|
|<span data-ttu-id="06f86-118">0</span><span class="sxs-lookup"><span data-stu-id="06f86-118">0</span></span>|<span data-ttu-id="06f86-119">Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.</span><span class="sxs-lookup"><span data-stu-id="06f86-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="06f86-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="06f86-120">1, 2, 3</span></span>|<span data-ttu-id="06f86-121">Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="06f86-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="06f86-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="06f86-122">4, 5, 6, 7</span></span>|<span data-ttu-id="06f86-123">Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="06f86-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="06f86-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="06f86-124">8, 9</span></span>|<span data-ttu-id="06f86-125">Die Nachricht stammt von einem Massen Absender, der eine hohe Anzahl von Beschwerden generiert.</span><span class="sxs-lookup"><span data-stu-id="06f86-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
