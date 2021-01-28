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
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029894"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="e9a1c-103">Beheben möglicher Einblicke in die E-Mail-Schleife im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e9a1c-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e9a1c-104">E-Mail-Schleifen sind ungültig, weil:</span><span class="sxs-lookup"><span data-stu-id="e9a1c-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="e9a1c-105">Sie verschwenden Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-105">They waste system resources.</span></span>
- <span data-ttu-id="e9a1c-106">Sie nutzen das E-Mail-Volumenkontingent Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="e9a1c-107">Sie senden verwirrende Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet) an die ursprünglichen Absender von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="e9a1c-108">The **Fix possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="e9a1c-109">Dieser Einblick wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="e9a1c-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Beheben der Einblicke in langsame Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="e9a1c-111">Wenn Sie im **Widget auf** Details anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e9a1c-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="e9a1c-112">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="e9a1c-112">**Domain**</span></span>
- <span data-ttu-id="e9a1c-113">**Anzahl der Nachrichten:**  Sie können auf [](message-trace-scc.md) "Beispielmeldungen anzeigen" klicken, um die Ergebnisse der Nachrichtenverfolgung für eine Stichprobe der Nachrichten zu sehen, die von der Schleife betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="e9a1c-114">**Domänentyp**" Beispielsweise autorisierend oder nicht autorisierend.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="e9a1c-115">**MX-Eintrag:** Der Host (**E-Mail-Server**) und **die Prioritätswerte** des MX-Eintrags für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="e9a1c-116">**Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span><span class="sxs-lookup"><span data-stu-id="e9a1c-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf "Details anzeigen" im Einblick "Mögliche E-Mail-Schleife korrigieren" geklickt haben](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="e9a1c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9a1c-118">See also</span></span>

<span data-ttu-id="e9a1c-119">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e9a1c-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
