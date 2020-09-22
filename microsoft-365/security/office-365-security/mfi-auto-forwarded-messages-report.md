---
title: Einblick in automatisch weitergeleitete Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: b5255a95718fa6624c85e93a19c8accf9c3dcdb2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199359"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="e004c-103">Einblicke automatisch weitergeleiteter Nachrichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e004c-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e004c-104">Die automatisch **weitergeleiteten Nachrichten** Insight im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die von Ihrer Organisation automatisch an Empfänger in externen domänenweiter geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e004c-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="e004c-106">Details zu automatisch weitergeleiteten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="e004c-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="e004c-107">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout-Bereich angezeigt, der weitere Informationen zu den automatisch weitergeleiteten Nachrichten zeigt:</span><span class="sxs-lookup"><span data-stu-id="e004c-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="e004c-108">**Nachrichten werden nach Weiterleitungs Methoden automatisch weitergeleitet**:</span><span class="sxs-lookup"><span data-stu-id="e004c-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="e004c-109">**Nachrichtenfluss Regeln**</span><span class="sxs-lookup"><span data-stu-id="e004c-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="e004c-110">**Nach Posteingangsregeln**</span><span class="sxs-lookup"><span data-stu-id="e004c-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="e004c-111">**Durch SMTP-Weiterleitung**</span><span class="sxs-lookup"><span data-stu-id="e004c-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="e004c-112">Einen Link zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report) für weitere Details.</span><span class="sxs-lookup"><span data-stu-id="e004c-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="e004c-113">**Automatisch weitergeleitete Nachrichten nach Domänen und Benutzern**:</span><span class="sxs-lookup"><span data-stu-id="e004c-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="e004c-114">**Top 5-domänenweiter geleitet an**</span><span class="sxs-lookup"><span data-stu-id="e004c-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="e004c-115">**Neue Domänen (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="e004c-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="e004c-116">**Die ersten 5 Weiterleitungs Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e004c-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="e004c-117">**Neue Benutzer (letzte Woche)**</span><span class="sxs-lookup"><span data-stu-id="e004c-117">**New users (last week)**</span></span>
  - <span data-ttu-id="e004c-118">Einen Link zum [Weiterleitungs Änderungsbericht](mfi-new-users-forwarding-email.md#forwarding-modifications-report) für weitere Details.</span><span class="sxs-lookup"><span data-stu-id="e004c-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details-Flyout für den Bericht "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="e004c-120">Insights</span><span class="sxs-lookup"><span data-stu-id="e004c-120">Insights</span></span>

<span data-ttu-id="e004c-121">Basierend auf den Berichtsdaten werden zwei Erkenntnisse generiert:</span><span class="sxs-lookup"><span data-stu-id="e004c-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="e004c-122">Neue Benutzer, die e-Mails weiterleiten</span><span class="sxs-lookup"><span data-stu-id="e004c-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="e004c-123">Neue Domänen, die e-Mail weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="e004c-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="e004c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e004c-124">See also</span></span>

<span data-ttu-id="e004c-125">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e004c-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
