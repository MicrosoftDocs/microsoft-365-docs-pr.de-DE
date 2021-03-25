---
title: Einblicke in Warteschlangen im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratoren können erfahren, wie Sie das Widget Warteschlangen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um den erfolglosen Nachrichtenfluss über ausgehende Connectors an ihre lokalen oder Partnerorganisationen zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206944"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="287bb-103">Einblicke in Warteschlangen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="287bb-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="287bb-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="287bb-104">**Applies to**</span></span>
- [<span data-ttu-id="287bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="287bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="287bb-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="287bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="287bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="287bb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="287bb-108">Wenn Nachrichten nicht über Connectors von Ihrer Organisation an Ihre lokalen oder Partner-E-Mail-Server gesendet werden können, werden die Nachrichten in Microsoft 365 in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="287bb-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="287bb-109">Häufige Beispiele, die diese Bedingung verursachen, sind:</span><span class="sxs-lookup"><span data-stu-id="287bb-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="287bb-110">Der Connector ist falsch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="287bb-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="287bb-111">In Ihrer lokalen Umgebung wurden Netzwerk- oder Firewalländerungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="287bb-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="287bb-112">Microsoft 365 wird weiterhin 24 Stunden lang die Zustellung wiederholen.</span><span class="sxs-lookup"><span data-stu-id="287bb-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="287bb-113">Nach 24 Stunden laufen die Nachrichten ab und werden in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bekannt) an die Absender zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="287bb-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="287bb-114">Wenn das E-Mail-Volume in der Warteschlange den vordefinierten Schwellenwert überschreitet (der Standardwert ist 200 Nachrichten), sind die Informationen an den folgenden Speicherorten verfügbar:</span><span class="sxs-lookup"><span data-stu-id="287bb-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="287bb-115">Der **Einblick in Warteschlangen** im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="287bb-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="287bb-116">Weitere Informationen finden Sie im [Abschnitt Warteschlangen im Abschnitt Nachrichtenflussdashboard](#queues-insight-in-the-mail-flow-dashboard) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="287bb-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="287bb-117">Eine Warnung wird im **Dashboard** "Benachrichtigungen" im [Security & Compliance Center](https://protection.office.com) (**Alerts** Dashboard oder \>  ) angezeigt. <https://protection.office.com/alertsdashboard></span><span class="sxs-lookup"><span data-stu-id="287bb-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Aktuelle Warnungen im Benachrichtigungsdashboard im Security & Compliance Center](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="287bb-119">Administratoren erhalten eine E-Mail-Benachrichtigung basierend auf der Konfiguration der Standardbenachrichtigungsrichtlinie mit dem Namen **Nachrichten wurden verzögert.**</span><span class="sxs-lookup"><span data-stu-id="287bb-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="287bb-120">Informationen zum Konfigurieren der Benachrichtigungseinstellungen für diese Warnung finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="287bb-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="287bb-121">Weitere Informationen zu Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="287bb-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="287bb-122">Anpassen von Warteschlangenwarnungen</span><span class="sxs-lookup"><span data-stu-id="287bb-122">Customize queue alerts</span></span>

1. <span data-ttu-id="287bb-123">Wechseln Sie [im Security & Compliance Center](https://protection.office.com)zu Warnungsbenachrichtigungsrichtlinien, oder öffnen Sie  \>  <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="287bb-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="287bb-124">Suchen Und **wählen Sie auf** der Seite Warnungsrichtlinien die Richtlinie mit dem Namen Nachrichten wurden **verzögert.**</span><span class="sxs-lookup"><span data-stu-id="287bb-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="287bb-125">Im **geöffneten Flyout** Message have been delayed können Sie die Warnung aktivieren oder deaktivieren und die Benachrichtigungseinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="287bb-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Nachrichten wurden verzögert Benachrichtigungsrichtlinie Details der Security & Compliance Center](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="287bb-127">**Status**: Sie können die Warnung ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="287bb-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="287bb-128">**E-Mail-Empfänger** **und Grenzwert für tägliche Benachrichtigungen**: Klicken Sie auf **Bearbeiten,** um die folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="287bb-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="287bb-129">Klicken Sie zum Konfigurieren der Benachrichtigungseinstellungen auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="287bb-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="287bb-130">Konfigurieren Sie **im angezeigten** Flyout Richtlinie bearbeiten die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="287bb-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="287bb-131">Senden von E-Mail-Benachrichtigungen: Der Standardwert ist aktiviert. </span><span class="sxs-lookup"><span data-stu-id="287bb-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="287bb-132">**E-Mail-Empfänger:** Der Standardwert ist **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="287bb-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="287bb-133">**Tägliches Benachrichtigungslimit:** Der Standardwert ist **No limit**.</span><span class="sxs-lookup"><span data-stu-id="287bb-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="287bb-134">**Schwellenwert**: Der Standardwert ist 200.</span><span class="sxs-lookup"><span data-stu-id="287bb-134">**Threshold**: The default value is 200.</span></span>

   ![Benachrichtigungseinstellungen in der Richtlinie "Nachrichten wurden verzögert" enthalten Details zum Security & Compliance Center](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="287bb-136">Klicken Sie nach Abschluss des Abschlusses **auf Speichern** und **Schließen.**</span><span class="sxs-lookup"><span data-stu-id="287bb-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="287bb-137">Einblicke in Warteschlangen im Nachrichtenflussdashboard</span><span class="sxs-lookup"><span data-stu-id="287bb-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="287bb-138">Auch wenn das Nachrichtenvolume in der Warteschlange den Schwellenwert nicht überschritten  und eine Warnung [](mail-flow-insights-v2.md) generiert hat, können Sie die Einblicke in Warteschlangen im Nachrichtenflussdashboard weiterhin verwenden, um Nachrichten anzuzeigen, die länger als eine Stunde in die Warteschlange eingereiht wurden, und Maßnahmen ergreifen, bevor die Anzahl der in die Warteschlange eingereihten Nachrichten zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="287bb-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Warteschlangen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-queues-widget.png)

<span data-ttu-id="287bb-140">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein **Flyout in** der Warteschlange für Nachrichten mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="287bb-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="287bb-141">**Anzahl der in die Warteschlange eingereihten Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="287bb-141">**Number of queued messages**</span></span>
- <span data-ttu-id="287bb-142">**Connectorname**: Klicken Sie auf den Connectornamen, um den Connector im Exchange Admin Center (EAC) zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="287bb-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="287bb-143">**Startzeit der Warteschlange**</span><span class="sxs-lookup"><span data-stu-id="287bb-143">**Queue started time**</span></span>
- <span data-ttu-id="287bb-144">**Älteste Nachrichten abgelaufen**</span><span class="sxs-lookup"><span data-stu-id="287bb-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="287bb-145">**Zielserver**</span><span class="sxs-lookup"><span data-stu-id="287bb-145">**Destination server**</span></span>
- <span data-ttu-id="287bb-146">**Letzte IP-Adresse**</span><span class="sxs-lookup"><span data-stu-id="287bb-146">**Last IP address**</span></span>
- <span data-ttu-id="287bb-147">**Letzter Fehler**</span><span class="sxs-lookup"><span data-stu-id="287bb-147">**Last error**</span></span>
- <span data-ttu-id="287bb-148">**So beheben Sie:** Häufige Probleme und Lösungen sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="287bb-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="287bb-149">Wenn ein **Link Jetzt beheben verfügbar** ist, klicken Sie darauf, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="287bb-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="287bb-150">Klicken Sie andernfalls auf alle verfügbaren Links, um weitere Informationen über den Fehler und mögliche Lösungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="287bb-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Details nach dem Klicken auf den Einblick in Warteschlangen im Nachrichtenflussdashboard](../../media/mfi-queues-details.png)

<span data-ttu-id="287bb-152">Das gleiche Flyout wird angezeigt, nachdem Sie **in** den Details einer Nachricht auf Warteschlange anzeigen geklickt **haben.**</span><span class="sxs-lookup"><span data-stu-id="287bb-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Nachrichten wurden im Security & Compliance Center verzögert](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="287bb-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="287bb-154">See also</span></span>

<span data-ttu-id="287bb-155">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="287bb-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
