---
title: Massenwerte für Reklamations Ebenen, Massenversender, BCL-Ebenen, Funktionsweise von BCL, BCL-Bewertungen, Antispam, Antispam-Header, Massen-e-Mail-Filterung, Massen-e-Mail-Stopp
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Informationen zu BCL-Werten (Bulk Complaint Level) in Office 365.
ms.openlocfilehash: 822c84ea9b36cfdae1d8faccf7e0c7d9f747c917
ms.sourcegitcommit: 7830969c8fa41724359657910716f3ce312cc2cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "37650117"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="92f5f-103">BCL-Werte (Bulk Complaint Level)</span><span class="sxs-lookup"><span data-stu-id="92f5f-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="92f5f-104">Versender von Massen-E-Mails arbeiten mit verschiedenen Sendemustern, Inhalterstellungsverfahren und Listenbeschaffungsarten.</span><span class="sxs-lookup"><span data-stu-id="92f5f-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="92f5f-105">Einige von ihnen sind gute Absender, die erwünschte Nachrichten mit relevantem Inhalt an Ihre Abonnenten senden.</span><span class="sxs-lookup"><span data-stu-id="92f5f-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="92f5f-106">Diese Nachrichten führen zu wenigen Beschwerden von Empfängern.</span><span class="sxs-lookup"><span data-stu-id="92f5f-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="92f5f-107">Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.</span><span class="sxs-lookup"><span data-stu-id="92f5f-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="92f5f-108">Um zwischen diesen Typen von Massen-E-Mail-Absendern zu unterscheiden, werden ihren Nachrichten BCL-Bewertungen (Bulk Complaint Level) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="92f5f-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="92f5f-109">BCL-Bewertungen können zwischen 1 und 9 liegen - je nachdem, wie wahrscheinlich es ist, dass die Massen-E-Mail zu Beschwerden führen.</span><span class="sxs-lookup"><span data-stu-id="92f5f-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="92f5f-110">Ein Absender mit dem BCL-Wert 9 wird wahrscheinlich mehr Beschwerden von Empfängern erhalten, was mit einem BCL-Wert von 3 wahrscheinlich nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="92f5f-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="92f5f-111">Microsoft arbeitet sowohl mit internen Quellen als auch mit Quellen von Drittanbietern, um die Absender von Massen-E-Mails zu identifizieren und den passenden BCL-Wert zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="92f5f-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="92f5f-112">Weitere Informationen zu dieser Nachrichtenkopfzeile finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="92f5f-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="92f5f-113">Da eine Massenwerbung mit einer Bewertung von 9 wahrscheinlich zu Reklamationen führen wird, ist die Standard-BCL 7.</span><span class="sxs-lookup"><span data-stu-id="92f5f-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="92f5f-114">Dies bedeutet, dass Massen-e-Mails erst dann akzeptiert werden, wenn die Reklamations Stufe 7 und die e-Mail danach nicht mehr akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="92f5f-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="92f5f-115">Je niedriger die Bewertung, desto weniger Massen-e-Mails werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="92f5f-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="92f5f-116">Wenn Ihre Benutzer sind und ihre Arbeit für Massen-e-Mails vertraulich ist und ihre BCL auf 4 festgelegt ist, werden keine Massen-e-Mails mit einer höheren BCL als 4 akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="92f5f-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="92f5f-117">Sie können BCL-Werte verwenden, um die für Ihre Organisation gewünschte Massenfilterungsebene festzulegen, indem Sie die Schritte unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md) befolgen.</span><span class="sxs-lookup"><span data-stu-id="92f5f-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="92f5f-118">In der folgenden Tabelle werden die derzeit verwendeten BCL-Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92f5f-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="92f5f-119">**BCL-Wert**</span><span class="sxs-lookup"><span data-stu-id="92f5f-119">**BCL Value**</span></span>|<span data-ttu-id="92f5f-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="92f5f-120">**Description**</span></span>|
|<span data-ttu-id="92f5f-121">0</span><span class="sxs-lookup"><span data-stu-id="92f5f-121">0</span></span>|<span data-ttu-id="92f5f-122">Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.</span><span class="sxs-lookup"><span data-stu-id="92f5f-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="92f5f-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="92f5f-123">1, 2, 3</span></span>|<span data-ttu-id="92f5f-124">Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="92f5f-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="92f5f-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="92f5f-125">4, 5, 6, 7</span></span>|<span data-ttu-id="92f5f-126">Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.</span><span class="sxs-lookup"><span data-stu-id="92f5f-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="92f5f-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="92f5f-127">8, 9</span></span>|<span data-ttu-id="92f5f-128">Die Nachricht stammt von einem Massen Absender, der eine hohe Anzahl von Beschwerden generiert.</span><span class="sxs-lookup"><span data-stu-id="92f5f-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
