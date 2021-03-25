---
title: Einblick in automatisch weitergeleitete Nachrichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206404"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="072f3-103">Einblicke in automatisch weitergeleitete Nachrichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="072f3-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="072f3-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="072f3-104">**Applies to**</span></span>
- [<span data-ttu-id="072f3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="072f3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="072f3-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="072f3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="072f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="072f3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="072f3-108">Der **Einblick** in automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die automatisch von Ihrer Organisation an Empfänger in externen Domänen weitergeleitet werden. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="072f3-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget für automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="072f3-110">Details zu automatisch weitergeleiteten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="072f3-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="072f3-111">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyoutbereich angezeigt, der weitere Informationen zu den automatisch weitergeleiteten Nachrichten enthält:</span><span class="sxs-lookup"><span data-stu-id="072f3-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="072f3-112">**Automatisch weitergeleitete Nachrichten durch Weiterleitungsmethoden**:</span><span class="sxs-lookup"><span data-stu-id="072f3-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="072f3-113">**Nach Nachrichtenflussregeln**</span><span class="sxs-lookup"><span data-stu-id="072f3-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="072f3-114">**Nach Posteingangsregeln**</span><span class="sxs-lookup"><span data-stu-id="072f3-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="072f3-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="072f3-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="072f3-116">Ein Link zum [Weiterleitungsbericht für](view-mail-flow-reports.md#forwarding-report) weitere Details.</span><span class="sxs-lookup"><span data-stu-id="072f3-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="072f3-117">**Automatisch weitergeleitete Nachrichten von Domänen und Benutzern**:</span><span class="sxs-lookup"><span data-stu-id="072f3-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="072f3-118">**Die 5 am besten weitergeleiteten Domänen**</span><span class="sxs-lookup"><span data-stu-id="072f3-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="072f3-119">**Neue Domänen (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="072f3-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="072f3-120">**Die 5 besten Weiterleitungsbenutzer**</span><span class="sxs-lookup"><span data-stu-id="072f3-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="072f3-121">**Neue Benutzer (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="072f3-121">**New users (last week)**</span></span>
  - <span data-ttu-id="072f3-122">Ein Link zum [Bericht "Weiterleitungsänderungen" für](mfi-new-users-forwarding-email.md#forwarding-modifications-report) weitere Details.</span><span class="sxs-lookup"><span data-stu-id="072f3-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details zum Flyout für den Bericht über automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="072f3-124">Einblicke</span><span class="sxs-lookup"><span data-stu-id="072f3-124">Insights</span></span>

<span data-ttu-id="072f3-125">Basierend auf den Berichtsdaten werden zwei Einblicke generiert:</span><span class="sxs-lookup"><span data-stu-id="072f3-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="072f3-126">Neue Benutzer, die E-Mails weiterleiten</span><span class="sxs-lookup"><span data-stu-id="072f3-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="072f3-127">Neue Domänen, die E-Mails weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="072f3-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="072f3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="072f3-128">See also</span></span>

<span data-ttu-id="072f3-129">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="072f3-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>