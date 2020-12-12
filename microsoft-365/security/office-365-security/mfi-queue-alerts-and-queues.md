---
title: Queues Insight im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratoren können erfahren, wie Sie das Warteschlangen-Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um den nicht erfolgreichen e-Mail-Fluss an Ihre lokalen oder Partnerorganisationen über ausgehende Connectors zu überwachen.
ms.openlocfilehash: a1563c61620ef9f1ae97739681f426fd0ea38bd8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659250"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="49171-103">Warteschlangen Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="49171-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="49171-104">Wenn Nachrichten nicht über Connectors von Ihrer Organisation an Ihre lokalen oder Partner-e-Mail-Server gesendet werden können, werden die Nachrichten in Microsoft 365 in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="49171-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="49171-105">Häufige Beispiele, die diese Bedingung verursachen, sind:</span><span class="sxs-lookup"><span data-stu-id="49171-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="49171-106">Der Connector ist nicht ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="49171-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="49171-107">In Ihrer lokalen Umgebung wurden Netzwerk-oder Firewall-Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="49171-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="49171-108">Microsoft 365 fährt fort, die Zustellung für 24 Stunden zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="49171-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="49171-109">Nach 24 Stunden laufen die Nachrichten ab und werden an die Absender in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Bounce-Nachrichten bezeichnet) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49171-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="49171-110">Wenn das e-Mail-Volumen in der Warteschlange den vordefinierten Schwellenwert überschreitet (der Standardwert ist 200 Nachrichten), stehen die Informationen an den folgenden Speicherorten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="49171-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="49171-111">Die **Queues** Insight im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="49171-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="49171-112">Weitere Informationen finden Sie im Abschnitt " [Queues Insight" im Abschnitt "Nachrichtenfluss-Dashboard](#queues-insight-in-the-mail-flow-dashboard) " in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="49171-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="49171-113">Im Alerts-Dashboard im [Security & Compliance Center](https://protection.office.com) (**Alerts** -Dashboard oder) wird eine **Warnung in den** Benachrichtigungen für Benachrichtigungen angezeigt \>  <https://protection.office.com/alertsdashboard> .</span><span class="sxs-lookup"><span data-stu-id="49171-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Aktuelle Benachrichtigungen im Alerts-Dashboard im Security & Compliance Center](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="49171-115">Administratoren erhalten eine e-Mail-Benachrichtigung basierend auf der Konfiguration der Standard Warnungs Richtlinie mit dem Namen " **Nachrichten wurden verzögert**.</span><span class="sxs-lookup"><span data-stu-id="49171-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="49171-116">Informationen zum Konfigurieren der Benachrichtigungseinstellungen für diese Warnung finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="49171-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="49171-117">Weitere Informationen zu Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49171-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="49171-118">Anpassen von Warteschlangen Warnungen</span><span class="sxs-lookup"><span data-stu-id="49171-118">Customize queue alerts</span></span>

1. <span data-ttu-id="49171-119">Wechseln Sie im [Security & Compliance Center](https://protection.office.com) **zu Alerts** \> **Alerts Policies** oder Open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="49171-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="49171-120">Suchen und wählen Sie auf der Seite " **Warnungsrichtlinien** " die Richtlinie mit dem Namen " **Nachrichten wurden verzögert**" aus.</span><span class="sxs-lookup"><span data-stu-id="49171-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="49171-121">In der **Meldung verzögertes** Flyout, das geöffnet wird, können Sie die Warnung aktivieren oder deaktivieren und die Benachrichtigungseinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49171-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Nachrichten wurden verzögert Warnungsrichtlinien Details das Security & Compliance Center](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="49171-123">**Status**: Sie können die Warnung aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="49171-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="49171-124">Grenzwert für **e-Mail-Empfänger** und **tägliche Benachrichtigung**: Klicken Sie auf **Bearbeiten** , um die folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="49171-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="49171-125">Klicken Sie auf **Bearbeiten**, um die Benachrichtigungseinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49171-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="49171-126">Konfigurieren Sie im eingeblendeten **Editor-Richtlinien** Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="49171-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="49171-127">**Senden von e-Mail-Benachrichtigungen**: der Standardwert ist "on".</span><span class="sxs-lookup"><span data-stu-id="49171-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="49171-128">**E-Mail-Empfänger**: der Standardwert ist **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="49171-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="49171-129">**Grenzwert für tägliche Benachrichtigung**: der Standardwert ist **No Limit**.</span><span class="sxs-lookup"><span data-stu-id="49171-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="49171-130">**Threshold**: der Standardwert ist 200.</span><span class="sxs-lookup"><span data-stu-id="49171-130">**Threshold**: The default value is 200.</span></span>

   ![Benachrichtigungseinstellungen in den Nachrichten wurden verzögert Warnungsrichtlinien Details das Security & Compliance Center](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="49171-132">Wenn Sie fertig sind, klicken Sie auf **Speichern** und **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="49171-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="49171-133">Queues Insight im Nachrichtenfluss-Dashboard</span><span class="sxs-lookup"><span data-stu-id="49171-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="49171-134">Auch wenn das Nachrichten Volume in der Warteschlange den Schwellenwert nicht überschreitet und eine Warnung generiert hat, können Sie weiterhin die **Warteschlangen** Einblicke im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) verwenden, um Nachrichten anzuzeigen, die länger als eine Stunde in die Warteschlange gestellt wurden, und Aktionen durchführen, bevor die Anzahl der in der Warteschlange befindlichen Nachrichten zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="49171-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Warteschlangen-Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-queues-widget.png)

<span data-ttu-id="49171-136">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout mit **Nachrichten in der Warteschlange** mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="49171-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="49171-137">**Anzahl von Nachrichten in der Warteschlange**</span><span class="sxs-lookup"><span data-stu-id="49171-137">**Number of queued messages**</span></span>
- <span data-ttu-id="49171-138">**Connectorname**: Klicken Sie auf den Namen des Connectors, um den Connector im Exchange Admin Center (EAC) zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="49171-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="49171-139">**Warteschlangen-Anfangszeit**</span><span class="sxs-lookup"><span data-stu-id="49171-139">**Queue started time**</span></span>
- <span data-ttu-id="49171-140">**Älteste Nachrichten abgelaufen**</span><span class="sxs-lookup"><span data-stu-id="49171-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="49171-141">**Zielserver**</span><span class="sxs-lookup"><span data-stu-id="49171-141">**Destination server**</span></span>
- <span data-ttu-id="49171-142">**Letzte IP-Adresse**</span><span class="sxs-lookup"><span data-stu-id="49171-142">**Last IP address**</span></span>
- <span data-ttu-id="49171-143">**Letzter Fehler**</span><span class="sxs-lookup"><span data-stu-id="49171-143">**Last error**</span></span>
- <span data-ttu-id="49171-144">**Beheben von** Problemen: häufige Probleme und Lösungen sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="49171-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="49171-145">Wenn es sich um einen **Fix-jetzt** -Link handelt, klicken Sie darauf, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="49171-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="49171-146">Klicken Sie andernfalls auf alle verfügbaren Links, um weitere Informationen zu dem Fehler und möglichen Lösungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="49171-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Details nach dem Klicken auf die Warteschlangen Insight im Nachrichtenfluss-Dashboard](../../media/mfi-queues-details.png)

<span data-ttu-id="49171-148">Das gleiche Flyout wird angezeigt, nachdem Sie in den Details einer **verzögerten Warnung Nachrichten** auf **Warteschlange anzeigen** klicken.</span><span class="sxs-lookup"><span data-stu-id="49171-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Nachrichten wurden im Security & Compliance Center mit Warnungsdetails verzögert](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="49171-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49171-150">See also</span></span>

<span data-ttu-id="49171-151">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="49171-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
