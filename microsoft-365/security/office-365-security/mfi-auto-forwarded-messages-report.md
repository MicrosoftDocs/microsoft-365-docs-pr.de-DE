---
title: Einblicke automatisch weitergeleitete Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: 05e3f62610c32bc95caf579ef4dd46bf1ed90275
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577819"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="f9ca9-103">Einblicke automatisch weitergeleiteter Nachrichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f9ca9-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="f9ca9-104">Die automatisch **weitergeleiteten Nachrichten** Insight im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zeigt Informationen zu Nachrichten an, die von Ihrer Organisation automatisch an Empfänger in externen domänenweiter geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f9ca9-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="f9ca9-106">Details zu automatisch weitergeleiteten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f9ca9-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="f9ca9-107">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout-Bereich angezeigt, der weitere Informationen zu den automatisch weitergeleiteten Nachrichten zeigt:</span><span class="sxs-lookup"><span data-stu-id="f9ca9-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="f9ca9-108">**Nachrichten werden nach Weiterleitungs Methoden automatisch weitergeleitet**:</span><span class="sxs-lookup"><span data-stu-id="f9ca9-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="f9ca9-109">**Nachrichtenfluss Regeln**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="f9ca9-110">**Nach Posteingangsregeln**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="f9ca9-111">**Durch SMTP-Weiterleitung**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="f9ca9-112">Einen Link zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report) für weitere Details.</span><span class="sxs-lookup"><span data-stu-id="f9ca9-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="f9ca9-113">**Automatisch weitergeleitete Nachrichten nach Domänen und Benutzern**:</span><span class="sxs-lookup"><span data-stu-id="f9ca9-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="f9ca9-114">**Top 5-domänenweiter geleitet an**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="f9ca9-115">**Neue Domänen (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="f9ca9-116">**Die ersten 5 Weiterleitungs Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="f9ca9-117">**Neue Benutzer (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="f9ca9-117">**New users (last week)**</span></span>
  - <span data-ttu-id="f9ca9-118">Einen Link zum [Weiterleitungs Änderungsbericht](mfi-new-users-forwarding-email.md#forwarding-modifications-report) für weitere Details.</span><span class="sxs-lookup"><span data-stu-id="f9ca9-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details-Flyout für den Bericht "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="f9ca9-120">Insights</span><span class="sxs-lookup"><span data-stu-id="f9ca9-120">Insights</span></span>

<span data-ttu-id="f9ca9-121">Basierend auf den Berichtsdaten werden zwei Erkenntnisse generiert:</span><span class="sxs-lookup"><span data-stu-id="f9ca9-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="f9ca9-122">Neue Benutzer, die e-Mails weiterleiten</span><span class="sxs-lookup"><span data-stu-id="f9ca9-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="f9ca9-123">Neue Domänen, die e-Mail weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="f9ca9-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="f9ca9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9ca9-124">See also</span></span>

<span data-ttu-id="f9ca9-125">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="f9ca9-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
