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
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Dashboard für den Nachrichtenfluss im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029942"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="dc5ab-103">Einblick in automatisch weitergeleitete Nachrichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc5ab-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc5ab-104">Der **Einblick** in automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die automatisch von Ihrer Organisation an Empfänger in externen Domänen weitergeleitet werden. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dc5ab-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget für automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="dc5ab-106">Details zu automatisch weitergeleiteten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="dc5ab-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="dc5ab-107">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyoutbereich mit weiteren Informationen zu den automatisch weitergeleiteten Nachrichten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dc5ab-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="dc5ab-108">**Automatisch weitergeleitete Nachrichten durch Weiterleitungsmethoden:**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="dc5ab-109">**Nach Nachrichtenflussregeln**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="dc5ab-110">**Nach Posteingangsregeln**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="dc5ab-111">**By SMTP forwarding:** This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="dc5ab-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="dc5ab-112">Ein Link zum [Weiterleitungsbericht für](view-mail-flow-reports.md#forwarding-report) weitere Details.</span><span class="sxs-lookup"><span data-stu-id="dc5ab-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="dc5ab-113">**Automatisch weitergeleitete Nachrichten von Domänen und Benutzern:**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="dc5ab-114">**Die 5 am besten weitergeleiteten Domänen**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="dc5ab-115">**Neue Domänen (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="dc5ab-116">**Top-5-Weiterleitungsbenutzer**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="dc5ab-117">**Neue Benutzer (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="dc5ab-117">**New users (last week)**</span></span>
  - <span data-ttu-id="dc5ab-118">Eine Verknüpfung zum [Bericht über Weiterleitungsänderungen,](mfi-new-users-forwarding-email.md#forwarding-modifications-report) um weitere Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dc5ab-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Detailf flyout für den Bericht über automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="dc5ab-120">Einblicke</span><span class="sxs-lookup"><span data-stu-id="dc5ab-120">Insights</span></span>

<span data-ttu-id="dc5ab-121">Basierend auf den Berichtsdaten werden zwei Einblicke generiert:</span><span class="sxs-lookup"><span data-stu-id="dc5ab-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="dc5ab-122">Neue Benutzer, die E-Mails weiterleiten</span><span class="sxs-lookup"><span data-stu-id="dc5ab-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="dc5ab-123">Neue Domänen, die per E-Mail weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="dc5ab-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="dc5ab-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc5ab-124">See also</span></span>

<span data-ttu-id="dc5ab-125">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dc5ab-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
