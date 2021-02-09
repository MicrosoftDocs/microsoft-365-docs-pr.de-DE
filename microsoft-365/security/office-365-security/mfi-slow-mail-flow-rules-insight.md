---
title: Beheben des Einblicks in langsame Nachrichtenflussregeln
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Einblick in langsame Nachrichtenflussregeln im Security & Compliance Center verwenden, um ineffiziente oder beschädigte Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150784"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="d29a5-103">Beheben von Einblicken in langsame Nachrichtenflussregeln im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d29a5-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d29a5-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="d29a5-104">**Applies to**</span></span>
- [<span data-ttu-id="d29a5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d29a5-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="d29a5-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="d29a5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="d29a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d29a5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d29a5-108">Ineffiziente Nachrichtenflussregeln (auch als Transportregeln bezeichnet) können zu Verzögerungen beim Nachrichtenfluss für Ihre Organisation führen.</span><span class="sxs-lookup"><span data-stu-id="d29a5-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="d29a5-109">In diesem Einblick werden Nachrichtenflussregeln berichtet, die sich auf den E-Mail-Fluss In Ihrer Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="d29a5-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="d29a5-110">Beispiele für diese Arten von Regeln sind:</span><span class="sxs-lookup"><span data-stu-id="d29a5-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="d29a5-111">Bedingungen, die **"Is" für große** Gruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a5-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="d29a5-112">Bedingungen, die den Mustervergleich komplexer regulärer Ausdrücke (regex) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a5-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="d29a5-113">Bedingungen, die die Inhaltsüberprüfung in Anlagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a5-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="d29a5-114">Der **Einblick** in den Einblick  in langsame [](mail-flow-insights-v2.md) Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss im Security [& Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn eine Nachrichtenflussregel zu lange zum Abschließen des Vorgangs ins Spiel kommt.</span><span class="sxs-lookup"><span data-stu-id="d29a5-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="d29a5-115">Dieser Einblick wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="d29a5-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="d29a5-116">Sie können diese Benachrichtigung verwenden, um Nachrichtenflussregeln zu identifizieren und zu optimieren, um Verzögerungen beim Nachrichtenfluss zu verringern.</span><span class="sxs-lookup"><span data-stu-id="d29a5-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Beheben der Einblicke in langsame Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="d29a5-118">Wenn Sie im **Widget auf Details** anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d29a5-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="d29a5-119">**Regel:** Sie können mit der Maus auf die Zusammenfassung zeigen, um alle Bedingungen, Ausnahmen und Aktionen der Regel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d29a5-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="d29a5-120">Sie können auf die Zusammenfassung klicken, um die Regel im Exchange Admin Center (EAC) zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d29a5-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="d29a5-121">**Anzahl der ausgewerteten** Nachrichten: Sie können [](message-trace-scc.md) auf "Beispielmeldungen anzeigen" klicken, um die Ergebnisse der Nachrichtenverfolgung für eine Stichprobe der nachrichten, die von der Regel betroffen waren, zu sehen. </span><span class="sxs-lookup"><span data-stu-id="d29a5-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="d29a5-122">**Durchschnittliche Zeit für jede Nachricht**</span><span class="sxs-lookup"><span data-stu-id="d29a5-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="d29a5-123">**Median der Zeit für eine** Nachricht: Der mittlere Wert, der die obere Hälfte von der unteren Hälfte der Zeitdaten trennt.</span><span class="sxs-lookup"><span data-stu-id="d29a5-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Details-Flyout, das nach dem Klicken auf "Details anzeigen" im Einblick "Langsamen Nachrichtenfluss beheben" angezeigt wird](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="d29a5-125">Weitere Informationen zu Bedingungen und Ausnahmen in Nachrichtenflussregeln finden Sie unter [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="d29a5-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="d29a5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d29a5-126">See also</span></span>

<span data-ttu-id="d29a5-127">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d29a5-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
