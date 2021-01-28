---
title: Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die Nachrichtenflussberichte informieren, die im Dashboard "Berichte" im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e69085d1fad845ab519f2590b0527316463373a7
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029798"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="e3940-103">Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e3940-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e3940-104">Zusätzlich zu den Nachrichtenflussberichten, [](mail-flow-insights-v2.md) die im E-Mail-Flussdashboard im Security & Compliance Center verfügbar sind, stehen im Dashboard "Berichte" verschiedene zusätzliche Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="e3940-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="e3940-105">Wenn Sie über die erforderlichen [Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im [Security & Compliance Center](https://protection.office.com) anzeigen, indem Sie zum Dashboard **"Berichte"** \> **gehen.**</span><span class="sxs-lookup"><span data-stu-id="e3940-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e3940-106">Um direkt zum Dashboard "Berichte" zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e3940-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="e3940-108">Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-108">Connector report</span></span>

<span data-ttu-id="e3940-109">Der **Connectorbericht zeigt** nachrichtenflussaktivitäten auf den eingehenden und ausgehenden [Connectors,](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e3940-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="e3940-110">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  den **Connectorbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="e3940-111">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="e3940-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorberichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="e3940-113">Berichtsansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-113">Report view for the Connector report</span></span>

<span data-ttu-id="e3940-114">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e3940-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="e3940-115">**Daten anzeigen nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, organisiert nach:</span><span class="sxs-lookup"><span data-stu-id="e3940-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="e3940-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="e3940-116">**Total**</span></span>
  - <span data-ttu-id="e3940-117">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e3940-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e3940-118">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e3940-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e3940-119">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="e3940-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="e3940-120">Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine dieser Optionen oder den **ganzen Nachrichtenfluss auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="e3940-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach Nachrichtenfluss im Connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="e3940-122">**Daten nach: TLS-Verwendung anzeigen:** Dieses Diagramm zeigt den Prozentsatz der Verwendung der Transport Layer Security (TLS)-Version für den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="e3940-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="e3940-123">Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine der folgenden Optionen auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="e3940-124">**Sämtlicher Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="e3940-124">**All mail flow**</span></span>
  - <span data-ttu-id="e3940-125">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e3940-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e3940-126">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e3940-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e3940-127">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="e3940-127">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im Connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="e3940-129">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="e3940-130">Detailtabelle für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-130">Details table view for the Connector report</span></span>

<span data-ttu-id="e3940-131">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3940-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e3940-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="e3940-132">**Date**</span></span>
- <span data-ttu-id="e3940-133">**Connectorrichtung und -name**</span><span class="sxs-lookup"><span data-stu-id="e3940-133">**Connector direction and name**</span></span>
- <span data-ttu-id="e3940-134">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="e3940-134">**Connector type**</span></span>
- <span data-ttu-id="e3940-135">**Erzwungenes TLS?**: Der Wert **True** oder **False**.</span><span class="sxs-lookup"><span data-stu-id="e3940-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="e3940-136">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e3940-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="e3940-137">**TLS 1.0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e3940-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="e3940-138">**TLS 1.1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e3940-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="e3940-139">**TLS 1.2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e3940-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="e3940-140">**Volume**: Die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e3940-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="e3940-141">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e3940-142">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="e3940-143">Bericht über Exchange-Transportregel</span><span class="sxs-lookup"><span data-stu-id="e3940-143">Exchange transport rule report</span></span>

<span data-ttu-id="e3940-144">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf eingehende und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e3940-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="e3940-145">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  die **Exchange-Transportregel aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="e3940-146">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="e3940-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e3940-148">Berichtsansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="e3940-149">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e3940-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="e3940-150">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Folgendem: Richtung:** Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e3940-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="e3940-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Schweregrad aufbrechen:** Dieses Diagramm  zeigt die Anzahl der Nachrichten mit hohem schweregrad und mittlerem Schweregrad und niedrigem **Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="e3940-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="e3940-152">Sie legen den Schweregrad als Aktion in der Regel **(Diese** Regel mit Schweregrad oder _SetAuditSeverity überwachen) festgelegt._</span><span class="sxs-lookup"><span data-stu-id="e3940-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="e3940-153">Weitere Informationen finden Sie unter Aktionen für [Nachrichtenflussregel in Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="e3940-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="e3940-154">**Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Nach Folgendem:** Richtung: Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e3940-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="e3940-155">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e3940-156">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="e3940-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e3940-157">**Anzeigen von Daten für: gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e3940-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e3940-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e3940-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="e3940-159">**Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Aufbrechen nach: Richtung:** Diese Ansicht zeigt die Anzahl der  Nachrichten mit hohem schweregrad und mittlerem Schweregrad sowie Nachrichten mit niedrigem Schweregrad, die von den DLP-Transportregeln betroffen waren. </span><span class="sxs-lookup"><span data-stu-id="e3940-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="e3940-160">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e3940-161">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="e3940-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e3940-162">**Anzeigen von Daten für: Gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e3940-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e3940-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e3940-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="e3940-164">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e3940-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="e3940-165">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e3940-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="e3940-166">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e3940-166">Direction values</span></span>
- <span data-ttu-id="e3940-167">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="e3940-167">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e3940-169">Detailtabelle für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="e3940-170">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="e3940-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e3940-171">**Anzeigen von Daten nach: Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="e3940-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="e3940-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="e3940-172">**Date**</span></span>
  - <span data-ttu-id="e3940-173">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e3940-173">**Transport rule**</span></span>
  - <span data-ttu-id="e3940-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="e3940-174">**Subject**</span></span>
  - <span data-ttu-id="e3940-175">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="e3940-175">**Sender address**</span></span>
  - <span data-ttu-id="e3940-176">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="e3940-176">**Recipient address**</span></span>
  - <span data-ttu-id="e3940-177">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="e3940-177">**Severity**</span></span>
  - <span data-ttu-id="e3940-178">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="e3940-178">**Direction**</span></span>

- <span data-ttu-id="e3940-179">**Anzeigen von Daten nach: DLP Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="e3940-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="e3940-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="e3940-180">**Date**</span></span>
  - <span data-ttu-id="e3940-181">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="e3940-181">**DLP policy**</span></span>
  - <span data-ttu-id="e3940-182">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e3940-182">**Transport rule**</span></span>
  - <span data-ttu-id="e3940-183">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="e3940-183">**Subject**</span></span>
  - <span data-ttu-id="e3940-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="e3940-184">**Sender address**</span></span>
  - <span data-ttu-id="e3940-185">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="e3940-185">**Recipient address**</span></span>
  - <span data-ttu-id="e3940-186">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="e3940-186">**Severity**</span></span>
  - <span data-ttu-id="e3940-187">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="e3940-187">**Direction**</span></span>

<span data-ttu-id="e3940-188">Wenn Sie in einer **Detailtabelle auf** "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e3940-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e3940-189">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e3940-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="e3940-190">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e3940-190">Direction values</span></span>
- <span data-ttu-id="e3940-191">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="e3940-191">Severity values</span></span>

<span data-ttu-id="e3940-192">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="e3940-193">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-193">Forwarding report</span></span>

<span data-ttu-id="e3940-194">Der **Weiterleitungsbericht zeigt** die automatisch weitergeleiteten Nachrichten Ihrer Organisation an externe Domänen aus Exchange Online-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="e3940-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="e3940-195">Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein gefährdetes Konto hinweisen.</span><span class="sxs-lookup"><span data-stu-id="e3940-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="e3940-196">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Berichtsdashboard, und wählen Sie  \>  **"Weiterleitungsbericht" aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="e3940-197">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="e3940-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget für Weiterleitungsbericht im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="e3940-199">Berichtsansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="e3940-200">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e3940-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e3940-201">**Daten für: Weiterleitungsmethoden anzeigen:** Die folgenden Methoden werden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3940-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="e3940-202">**Transportregel:** Auch als [Nachrichtenflussregeln bezeichnet.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e3940-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="e3940-203">**Postfachregel:** Auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="e3940-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="e3940-205">**Daten anzeigen für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.</span><span class="sxs-lookup"><span data-stu-id="e3940-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Domänen weiterleiten" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="e3940-207">**Anzeigen von Daten für: Weiterleitungen:** Die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3940-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="e3940-208">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e3940-208">**Transport rule**</span></span>
  - <span data-ttu-id="e3940-209">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="e3940-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Weiterleitungsansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="e3940-211">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="e3940-212">Detailtabelle für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="e3940-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="e3940-213">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3940-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e3940-214">**Weiterleitungen:** Der Wert **der Transportregel** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="e3940-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="e3940-215">**Weiterleitungstyp:** Der Wert **Postfachregel oder** **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="e3940-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="e3940-216">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="e3940-216">**Recipient name**</span></span>
- <span data-ttu-id="e3940-217">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="e3940-217">**Recipient domain**</span></span>
- <span data-ttu-id="e3940-218">**Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="e3940-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="e3940-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-219">**Count**</span></span>
- <span data-ttu-id="e3940-220">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="e3940-220">**First forward date**</span></span>

<span data-ttu-id="e3940-221">Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e3940-222">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e3940-223">Statusbericht über den Nachrichtenfluss</span><span class="sxs-lookup"><span data-stu-id="e3940-223">Mailflow status report</span></span>

<span data-ttu-id="e3940-224">Der **Statusbericht "E-Mail-Nachrichtenfluss"** ähnelt dem Bericht "Gesendete und empfangene E-Mail", [](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die auf dem Edge zulässig oder blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="e3940-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="e3940-225">Dies ist der einzige Bericht, der Informationen zum Edgeschutz enthält und zeigt, wie viele E-Mails blockiert werden, bevor sie zur Evaluierung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="e3940-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e3940-226">Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="e3940-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="e3940-227">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Berichtsdashboard, und wählen Sie den Statusbericht für den  \>  **Nachrichtenfluss aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="e3940-228">Um direkt zum Statusbericht für den **Nachrichtenfluss zu wechseln,** öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="e3940-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Bericht "E-Mail-Statusbericht" im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="e3940-230">Typansicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="e3940-231">Wenn Sie den Bericht öffnen, ist die Registerkarte **"Typ"** standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e3940-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="e3940-232">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e3940-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e3940-233">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e3940-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="e3940-234">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="e3940-234">**Direction**:</span></span>

  - <span data-ttu-id="e3940-235">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="e3940-235">**Inbound**</span></span>
  - <span data-ttu-id="e3940-236">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="e3940-236">**Outbound**</span></span>
  - <span data-ttu-id="e3940-237">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="e3940-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e3940-238">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von **ein-** und ausgehend **gezählt)**</span><span class="sxs-lookup"><span data-stu-id="e3940-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="e3940-239">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="e3940-239">**Type**:</span></span>

  - <span data-ttu-id="e3940-240">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-240">**Good mail**</span></span>
  - <span data-ttu-id="e3940-241">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="e3940-241">**Malware**</span></span>
  - <span data-ttu-id="e3940-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="e3940-242">**Spam**</span></span>
  - <span data-ttu-id="e3940-243">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="e3940-243">**Edge protection**</span></span>
  - <span data-ttu-id="e3940-244">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="e3940-244">**Rule messages**</span></span>
  - <span data-ttu-id="e3940-245">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-245">**Phishing email**</span></span>

<span data-ttu-id="e3940-246">Das Diagramm ist nach den **Typwerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="e3940-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="e3940-247">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="e3940-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="e3940-248">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e3940-248">The data table contains the following information:</span></span>

- <span data-ttu-id="e3940-249">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="e3940-249">**Direction**</span></span>
- <span data-ttu-id="e3940-250">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e3940-250">**Type**</span></span>
- <span data-ttu-id="e3940-251">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="e3940-251">**24 hours**</span></span>
- <span data-ttu-id="e3940-252">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="e3940-252">**3 days**</span></span>
- <span data-ttu-id="e3940-253">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="e3940-253">**7 days**</span></span>
- <span data-ttu-id="e3940-254">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="e3940-254">**15 days**</span></span>
- <span data-ttu-id="e3940-255">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="e3940-255">**30 days**</span></span>

<span data-ttu-id="e3940-256">Wenn Sie **auf "Kategorie auswählen" klicken,** können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="e3940-257">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e3940-258">**Schadsoftware in** E-Mail: Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e3940-259">**Spamerkennungen:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="e3940-260">**Blockierte Spam-Edge-Nachricht:** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e3940-261">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="e3940-261">**Export**:</span></span>

<span data-ttu-id="e3940-262">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="e3940-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e3940-263">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3940-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e3940-264">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e3940-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e3940-265">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3940-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e3940-266">Typansicht im Statusbericht "Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="e3940-267">Richtungsansicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="e3940-268">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden dieselben Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3940-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="e3940-269">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="e3940-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="e3940-270">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="e3940-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="e3940-271">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3940-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="e3940-272">Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="e3940-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="e3940-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="e3940-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="e3940-274">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="e3940-274">**Export**:</span></span>

<span data-ttu-id="e3940-275">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="e3940-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e3940-276">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3940-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e3940-277">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e3940-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e3940-278">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3940-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e3940-279">Richtungsansicht im Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="e3940-280">Trichteransicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="e3940-281">Die **Trichteransicht** zeigt, wie die Features zum Schutz vor E-Mail-Bedrohungen von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="e3940-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="e3940-282">Sie enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfunktionen, einschließlich Edgeschutz, Ansoftware, Antiphishing, Antispam und Antis spoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="e3940-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="e3940-283">Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e3940-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e3940-284">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e3940-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e3940-285">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="e3940-285">**Direction**:</span></span>

  - <span data-ttu-id="e3940-286">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="e3940-286">**Inbound**</span></span>
  - <span data-ttu-id="e3940-287">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="e3940-287">**Outbound**</span></span>
  - <span data-ttu-id="e3940-288">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. absender abc@domain.com an empfänger-xyz@domain.com (separat von ein- und ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="e3940-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="e3940-289">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e3940-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e3940-290">Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="e3940-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e3940-291">Dieses Diagramm zeigt die Anzahl der E-Mails, organisiert nach:</span><span class="sxs-lookup"><span data-stu-id="e3940-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="e3940-292">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-292">**Total email**</span></span>
- <span data-ttu-id="e3940-293">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="e3940-293">**Email after edge protection**</span></span>
- <span data-ttu-id="e3940-294">**E-Mail nach Ansoftware, Datei-Reputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="e3940-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="e3940-295">**E-Mail nach Anti phish, URL-Reputation, Markenwechsel, Antis spoofing**</span><span class="sxs-lookup"><span data-stu-id="e3940-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="e3940-296">**E-Mail nach Antispam, Massen-E-Mail-Filterung**</span><span class="sxs-lookup"><span data-stu-id="e3940-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="e3940-297">**E-Mail nach Benutzer- und Domänenwechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3940-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="e3940-298">**E-Mail nach Datei- und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3940-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="e3940-299">**E-Mail, die nach dem Schutz nach der Zustellung als gutartig erkannt wurde (URL-Klickzeitschutz)**</span><span class="sxs-lookup"><span data-stu-id="e3940-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="e3940-300"><sup>Nur 1</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e3940-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="e3940-301">Um die von EOP oder Defender für Office 365 gefilterte E-Mail separat anzeigen zu können, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="e3940-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="e3940-302">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="e3940-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e3940-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="e3940-303">**Date**</span></span>
- <span data-ttu-id="e3940-304">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-304">**Total email**</span></span>
- <span data-ttu-id="e3940-305">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="e3940-305">**Edge protection**</span></span>
- <span data-ttu-id="e3940-306">**An malware, file reputation, file type block**:</span><span class="sxs-lookup"><span data-stu-id="e3940-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="e3940-307">**Datei-Reputation:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei durch andere Kunden von Microsoft gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3940-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="e3940-308">**Dateitypblock:** Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3940-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="e3940-309">**Anti phish, URL reputation, Brand impersonation, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="e3940-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="e3940-310">**URL-Reputation:** Nachrichten, die aufgrund der Identifizierung der URL durch andere Kunden von Microsoft gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3940-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="e3940-311">**Markenwechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Marken imitierenden Absendern stammt.</span><span class="sxs-lookup"><span data-stu-id="e3940-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="e3940-312">**Antis spoof:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne, der der Empfänger angehört, oder eine Domäne zu spoofieren, die dem Nachrichtensender nicht gehört.</span><span class="sxs-lookup"><span data-stu-id="e3940-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="e3940-313">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="e3940-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="e3940-314">**Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs, Massen-E-Mails an die Empfänger zu senden, gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3940-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="e3940-315">**Identitätswechsel von Benutzern und Domänen (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="e3940-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e3940-316">**Benutzer-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, die Identität eines Benutzers (Nachrichtensenders) zu imitieren, der in den Identitätsschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e3940-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="e3940-317">**Domänen-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e3940-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="e3940-318">**Datei- und URL-Detonation (Defender für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e3940-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e3940-319">**Dateidetonation:** Nachrichten, die durch eine Richtlinie für sichere Anlagen gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3940-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="e3940-320">**URL-Detonation:** Nachricht, gefiltert durch eine Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="e3940-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="e3940-321">**Post delivery protection and ZAP (ATP) or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span><span class="sxs-lookup"><span data-stu-id="e3940-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="e3940-322">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e3940-323">**Export:**</span><span class="sxs-lookup"><span data-stu-id="e3940-323">**Export**:</span></span>

<span data-ttu-id="e3940-324">Nachdem Sie unter **"Optionen"** **auf**"Exportieren" geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="e3940-325">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e3940-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e3940-326">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e3940-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e3940-327">Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="e3940-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e3940-328">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3940-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e3940-329">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e3940-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e3940-330">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3940-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e3940-331">Trichteransicht im Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="e3940-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="e3940-332">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="e3940-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="e3940-333">Die **technische Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Features für den Bedrohungsschutz.</span><span class="sxs-lookup"><span data-stu-id="e3940-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="e3940-334">Anhand des Diagramms können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3940-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="e3940-335">Wenn Sie auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e3940-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e3940-336">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e3940-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e3940-337">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="e3940-337">**Direction**:</span></span>

  - <span data-ttu-id="e3940-338">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="e3940-338">**Inbound**</span></span>
  - <span data-ttu-id="e3940-339">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="e3940-339">**Outbound**</span></span>
  - <span data-ttu-id="e3940-340">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="e3940-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e3940-341">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von ein- und ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="e3940-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="e3940-342">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e3940-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e3940-343">Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="e3940-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e3940-344">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="e3940-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="e3940-345">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-345">**Total email**</span></span>
- <span data-ttu-id="e3940-346">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="e3940-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="e3940-347">**Keine Schadsoftware,** **Erkennung sicherer Anlagen,** Erkennung von An <sup>\*</sup> **malwaremodulen** und **Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="e3940-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="e3940-348">**Kein Phishing,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishingerkennung**</span><span class="sxs-lookup"><span data-stu-id="e3940-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="e3940-349">**Keine Erkennung mit URL-Detonation** und **ERKENNUNG der URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3940-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="e3940-350">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="e3940-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="e3940-351">**Nicht schädliche E-Mails,** **Erkennung sicherer** <sup>\*</sup> Links und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="e3940-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="e3940-352"><sup>\*</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e3940-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="e3940-353">Wenn Sie mit der Maus auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="e3940-354">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="e3940-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e3940-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="e3940-355">**Date**</span></span>
- <span data-ttu-id="e3940-356">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-356">**Total email**</span></span>
- <span data-ttu-id="e3940-357">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="e3940-357">**Edge filtered**</span></span>
- <span data-ttu-id="e3940-358">**An malware engine, Safe Attachments, rule filtered**:</span><span class="sxs-lookup"><span data-stu-id="e3940-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="e3940-359">**Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="e3940-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="e3940-360">**DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="e3940-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="e3940-361">**DMARC:** Nachrichten, die gefiltert wurden, weil die Nachricht die DMARC-Authentifizierungsprüfung nicht hat.</span><span class="sxs-lookup"><span data-stu-id="e3940-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="e3940-362">**Erkennung der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="e3940-362">**URL detonation detection**</span></span>
- <span data-ttu-id="e3940-363">**Antispamfilter**</span><span class="sxs-lookup"><span data-stu-id="e3940-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="e3940-364">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="e3940-364">**ZAP removed**</span></span>
- <span data-ttu-id="e3940-365">**Erkennung durch sichere Links**</span><span class="sxs-lookup"><span data-stu-id="e3940-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="e3940-366">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e3940-367">**Export:**</span><span class="sxs-lookup"><span data-stu-id="e3940-367">**Export**:</span></span>

<span data-ttu-id="e3940-368">Wenn Sie auf **"Exportieren"** **klicken,** können Sie unter "Optionen" einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="e3940-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="e3940-369">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e3940-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e3940-370">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e3940-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e3940-371">Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="e3940-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e3940-372">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3940-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e3940-373">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e3940-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e3940-374">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3940-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e3940-375">Tech view in the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="e3940-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e3940-376">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="e3940-376">Sent and received email report</span></span>

<span data-ttu-id="e3940-377">Der **Bericht "Gesendete** und empfangene E-Mail" ist ein intelligenter Bericht mit Informationen zu eingehenden und ausgehenden E-Mails, einschließlich Spamerkennungen, Schadsoftware und als "gut" gekennzeichneter E-Mails.</span><span class="sxs-lookup"><span data-stu-id="e3940-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="e3940-378">Der Unterschied zwischen diesem [](#mailflow-status-report) Bericht und dem Statusbericht zum E-Mail-Nachrichtenfluss ist: Dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="e3940-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="e3940-379">Die Aggregatansicht und die Detailansicht des Berichts lassen eine Filterung von 90 Tagen zu.</span><span class="sxs-lookup"><span data-stu-id="e3940-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="e3940-380">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie "Gesendete und empfangene E-Mail"  \>  **aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="e3940-381">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="e3940-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e3940-383">Berichtsansicht für den Bericht "Gesendete und empfangene E-Mail"</span><span class="sxs-lookup"><span data-stu-id="e3940-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="e3940-384">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e3940-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e3940-385">**Aufteilen nach: Typ**: Das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="e3940-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="e3940-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="e3940-386">**Total**</span></span>
  - <span data-ttu-id="e3940-387">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e3940-387">**Good mail**</span></span>
  - <span data-ttu-id="e3940-388">**Schadsoftware (Ansoftware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e3940-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="e3940-389">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="e3940-389">**Spam detections**</span></span>
  - <span data-ttu-id="e3940-390">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="e3940-390">**Rule messages**</span></span>
  - <span data-ttu-id="e3940-391">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="e3940-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="e3940-392">Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="e3940-394">**Aufbrechen nach: Richtung:** Das Diagramm zeigt **Daten gesamt,** **ein-** und **ausgehend.**</span><span class="sxs-lookup"><span data-stu-id="e3940-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="e3940-395">Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="e3940-397">**Drilldown nach** \> **Schadsoftware (Ansoftware):** Diese Auswahl führt Sie zu den [Schadsoftwareerkennungen im E-Mail-Bericht.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="e3940-398">**Drilldown nach** \> **Spamerkennungen):** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e3940-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e3940-399">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e3940-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e3940-400">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e3940-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="e3940-401">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e3940-401">Direction values</span></span>
- <span data-ttu-id="e3940-402">Typwerte</span><span class="sxs-lookup"><span data-stu-id="e3940-402">Type values</span></span>

<span data-ttu-id="e3940-403">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e3940-404">Detailtabelle für den Bericht "Gesendete und empfangene E-Mail"</span><span class="sxs-lookup"><span data-stu-id="e3940-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="e3940-405">Wenn Sie in der **Tabelle "Details anzeigen"** in der Tabelle "Nach: Richtung oder Nach unten  **nach:** Richtungsansicht" klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e3940-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="e3940-406">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="e3940-406">**Date (UTC)**</span></span>
- <span data-ttu-id="e3940-407">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e3940-407">**Type**</span></span>
- <span data-ttu-id="e3940-408">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="e3940-408">**Direction**</span></span>
- <span data-ttu-id="e3940-409">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e3940-409">**Message count**</span></span>

<span data-ttu-id="e3940-410">Wenn Sie in einer **Detailtabelle** auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e3940-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e3940-411">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e3940-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="e3940-412">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e3940-412">Direction values</span></span>
- <span data-ttu-id="e3940-413">Typwerte</span><span class="sxs-lookup"><span data-stu-id="e3940-413">Type values</span></span>

<span data-ttu-id="e3940-414">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e3940-415">Bericht zu den am besten verwendeten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="e3940-415">Top senders and recipients report</span></span>

<span data-ttu-id="e3940-416">Der **Bericht "Die besten Absender und Empfänger"** ist ein Kreisdiagramm, in dem Die besten E-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3940-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="e3940-417">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie  \>  **"Top senders and recipients" aus.**</span><span class="sxs-lookup"><span data-stu-id="e3940-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="e3940-418">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="e3940-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Das Widget mit den besten Absendern und Empfängern im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e3940-420">Berichtsansicht für den Bericht der obersten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="e3940-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="e3940-421">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e3940-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e3940-422">**Anzeigen von Daten für \> die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e3940-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="e3940-423">**Anzeigen von Daten für \> die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="e3940-424">**Anzeigen von Daten für \> die obersten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="e3940-425">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="e3940-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="e3940-426">**Anzeigen von Daten für \> die am besten verwendeten Schadsoftwareempfänger (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e3940-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="e3940-427">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlen.</span><span class="sxs-lookup"><span data-stu-id="e3940-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="e3940-428">Wenn Sie im Kreisdiagramm auf einen Spalt zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3940-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="e3940-429">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht über die obersten Absender und Empfänger](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e3940-431">Detailtabelle für den Bericht zu den obersten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="e3940-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="e3940-432">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="e3940-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e3940-433">**Anzeigen von Daten für \> die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e3940-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="e3940-434">**Die am besten verwendeten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e3940-434">**Top mail senders**</span></span>
  - <span data-ttu-id="e3940-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-435">**Count**</span></span>

- <span data-ttu-id="e3940-436">**Anzeigen von Daten für \> die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="e3940-437">**Die am besten verwendeten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="e3940-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-438">**Count**</span></span>

- <span data-ttu-id="e3940-439">**Anzeigen von Daten für \> die obersten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="e3940-440">**Die am besten erhaltenen Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="e3940-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-441">**Count**</span></span>

- <span data-ttu-id="e3940-442">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="e3940-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="e3940-443">**Am besten für Schadsoftwareempfänger**</span><span class="sxs-lookup"><span data-stu-id="e3940-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="e3940-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-444">**Count**</span></span>

- <span data-ttu-id="e3940-445">**Anzeigen von Daten für \> die am besten verwendeten Schadsoftwareempfänger (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e3940-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="e3940-446">**Am besten für Schadsoftwareempfänger (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e3940-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="e3940-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="e3940-447">**Count**</span></span>

<span data-ttu-id="e3940-448">Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="e3940-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e3940-449">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="e3940-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e3940-450">Welche Berechtigungen sind erforderlich, um diese Berichte anzeigen zu können?</span><span class="sxs-lookup"><span data-stu-id="e3940-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e3940-451">Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="e3940-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e3940-452">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="e3940-452">**Organization Management**</span></span>
- <span data-ttu-id="e3940-453">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="e3940-453">**Security Administrator**</span></span>
- <span data-ttu-id="e3940-454">**Sicherheitsleseprogramm**</span><span class="sxs-lookup"><span data-stu-id="e3940-454">**Security Reader**</span></span>
- <span data-ttu-id="e3940-455">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="e3940-455">**Global Reader**</span></span>

<span data-ttu-id="e3940-456">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e3940-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e3940-457">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3940-457">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e3940-458">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e3940-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3940-459">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e3940-459">Related topics</span></span>

[<span data-ttu-id="e3940-460">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e3940-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e3940-461">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e3940-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="e3940-462">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e3940-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e3940-463">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e3940-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
