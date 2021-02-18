---
title: Beheben eines möglichen Einblicks in den E-Mail-Loop
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Einblick in mögliche E-Mail-Schleifen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Schleifen in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290561"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="973b5-103">Beheben möglicher Einblicke in die E-Mail-Schleife im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="973b5-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="973b5-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="973b5-104">**Applies to**</span></span>
- [<span data-ttu-id="973b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="973b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="973b5-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="973b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="973b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="973b5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="973b5-108">E-Mail-Schleifen sind ungültig, weil:</span><span class="sxs-lookup"><span data-stu-id="973b5-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="973b5-109">Sie verschwenden Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="973b5-109">They waste system resources.</span></span>
- <span data-ttu-id="973b5-110">Sie nutzen das E-Mail-Volumenkontingent Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="973b5-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="973b5-111">Sie senden verwirrende Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet) an die ursprünglichen Absender von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="973b5-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="973b5-112">The **Fix possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span><span class="sxs-lookup"><span data-stu-id="973b5-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="973b5-113">Dieser Einblick wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="973b5-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Beheben der Einblicke in langsame Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="973b5-115">Wenn Sie im **Widget auf Details** anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="973b5-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="973b5-116">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="973b5-116">**Domain**</span></span>
- <span data-ttu-id="973b5-117">**Anzahl der Nachrichten:**  Sie können auf [](message-trace-scc.md) "Beispielmeldungen anzeigen" klicken, um die Ergebnisse der Nachrichtenverfolgung für eine Stichprobe der Nachrichten zu sehen, die von der Schleife betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="973b5-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="973b5-118">**Domänentyp**" Beispielsweise autorisierend oder nicht autorisierend.</span><span class="sxs-lookup"><span data-stu-id="973b5-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="973b5-119">**MX-Eintrag:** Der Host (**E-Mail-Server**) und **die Prioritätswerte** des MX-Eintrags für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="973b5-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="973b5-120">**Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span><span class="sxs-lookup"><span data-stu-id="973b5-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf "Details anzeigen" im Einblick "Mögliche E-Mail-Schleife korrigieren" geklickt haben](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="973b5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="973b5-122">See also</span></span>

<span data-ttu-id="973b5-123">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="973b5-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
