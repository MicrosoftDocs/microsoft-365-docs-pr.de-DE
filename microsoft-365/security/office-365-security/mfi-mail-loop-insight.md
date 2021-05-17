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
description: Administratoren erfahren, wie Sie den Einblick in mögliche E-Mail-Schleifen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Schleifen in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206344"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="8970f-103">Beheben möglicher Einblicke in die E-Mail-Schleife im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8970f-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8970f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8970f-104">**Applies to**</span></span>
- [<span data-ttu-id="8970f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8970f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8970f-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8970f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8970f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8970f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8970f-108">E-Mail-Schleifen sind schlecht, da:</span><span class="sxs-lookup"><span data-stu-id="8970f-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="8970f-109">Sie verschwenden Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="8970f-109">They waste system resources.</span></span>
- <span data-ttu-id="8970f-110">Sie nutzen das E-Mail-Volumenkontingent Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8970f-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="8970f-111">Sie senden verwirrende Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) an die ursprünglichen Nachrichtensender.</span><span class="sxs-lookup"><span data-stu-id="8970f-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="8970f-112">Der Einblick in mögliche  **E-Mail-Schleifen** [](mail-flow-insights-v2.md) beheben im Bereich Empfohlen für Sie des Nachrichtenflussdashboards im Security & Compliance Center benachrichtigt Sie, wenn eine E-Mail-Schleife in Ihrer Organisation erkannt wird. [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="8970f-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="8970f-113">Diese Einsicht wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="8970f-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Beheben des Einblicks zu langsamen Nachrichtenflussregeln im Bereich Empfohlen für Sie im Dashboard für den Nachrichtenfluss](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="8970f-115">Wenn Sie auf **Details im** Widget anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8970f-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="8970f-116">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8970f-116">**Domain**</span></span>
- <span data-ttu-id="8970f-117">**Anzahl der Nachrichten**: Sie können auf [](message-trace-scc.md) Beispielnachrichten **anzeigen** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der Nachrichten zu sehen, die von der Schleife betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="8970f-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="8970f-118">**Domänentyp**" Beispiel: Autoritative oder nicht autorisierende.</span><span class="sxs-lookup"><span data-stu-id="8970f-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="8970f-119">**MX-Eintrag:** Die Werte host (**Mail server**) und **Priority** des MX-Eintrags für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="8970f-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="8970f-120">**Loop reason** und **How to fix**: Wir identifizieren die gängigsten Szenarien für E-Mail-Schleifen und bieten empfohlene Aktionen zum Beheben der Schleife.</span><span class="sxs-lookup"><span data-stu-id="8970f-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details in der Möglichen E-Mail-Schleife korrigieren geklickt haben](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="8970f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8970f-122">See also</span></span>

<span data-ttu-id="8970f-123">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8970f-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
