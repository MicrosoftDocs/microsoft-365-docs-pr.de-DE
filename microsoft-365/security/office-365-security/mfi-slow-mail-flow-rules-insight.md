---
title: Beheben des Einblicks in langsame Nachrichtenflussregeln
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie in Ihrer Organisation die Informationen zum Fix Slow Mail Flow Rules Insight im Security & Compliance Center verwenden, um ineffiziente oder fehlerhafte Nachrichtenfluss Regeln (auch bekannt als Transportregeln) zu identifizieren und zu beheben.
ms.openlocfilehash: 6a2a3c42eadf3c621b34d2a21344eafd2618e669
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877537"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="19369-103">Beheben langsamer Nachrichtenfluss Regeln Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="19369-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="19369-104">Ineffiziente Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) können zu Verzögerungen bei der Nachrichtenübermittlung für Ihre Organisation führen.</span><span class="sxs-lookup"><span data-stu-id="19369-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="19369-105">Diese Einblicke meldet Nachrichtenfluss Regeln, die sich auf den e-Mail-Fluss Ihrer Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="19369-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="19369-106">Beispiele für diese Regeltypen sind:</span><span class="sxs-lookup"><span data-stu-id="19369-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="19369-107">Die Bedingungen, die verwendet **werden, sind Mitglied von** für große Gruppen.</span><span class="sxs-lookup"><span data-stu-id="19369-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="19369-108">Bedingungen, die einen komplexen Regular Expression (Regex)-Mustervergleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="19369-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="19369-109">Bedingungen, die die Inhaltsüberprüfung in Anlagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="19369-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="19369-110">Die **Fix langsamen Nachrichtenfluss Regeln** Einblicke in den Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn eine e-Mail-Fluss Regel zu lange dauert, bis Sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="19369-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="19369-111">Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="19369-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="19369-112">Sie können diese Benachrichtigung verwenden, um e-Mail-Flussregeln zu identifizieren und zu optimieren, um Verzögerungen bei der Nachrichtenübermittlung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="19369-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="19369-114">Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="19369-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="19369-115">**Regel** : Sie können mit dem Mauszeiger auf die Zusammenfassung zeigen, um alle Bedingungen, Ausnahmen und Aktionen der Regel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19369-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="19369-116">Sie können auf die Zusammenfassung klicken, um die Regel im Exchange Admin Center (EAC) zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="19369-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="19369-117">**Anzahl ausgewerteter Nachrichten** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Regel betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="19369-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="19369-118">**Durchschnittliche Zeitaufwand für jede Nachricht**</span><span class="sxs-lookup"><span data-stu-id="19369-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="19369-119">**Für eine Nachricht aufgewendete mittlere Zeit** : der mittlere Wert, der die obere Hälfte von der unteren Hälfte der Zeit Daten trennt.</span><span class="sxs-lookup"><span data-stu-id="19369-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Details-Flyout, das nach dem Klicken auf Details anzeigen im Fix Slow Mail Flow Rules Insight angezeigt wird](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="19369-121">Weitere Informationen zu Bedingungen und Ausnahmen in Nachrichtenfluss Regeln in Exchange Online finden Sie unter [Mail Flow rule conditions and Exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="19369-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19369-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="19369-122">Related topics</span></span>

<span data-ttu-id="19369-123">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="19369-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
