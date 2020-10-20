---
title: Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den Nachrichtenfluss Berichten erhalten, die im Dashboard Berichte im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.openlocfilehash: 801463877db2e022ab84c3187367587c61f71090
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600592"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="e6def-103">Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e6def-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e6def-104">Zusätzlich zu den Nachrichtenfluss Berichten, die im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zur Verfügung stehen, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenübermittlungs Berichte zur Verfügung, mit denen Sie Ihre Microsoft 365-Organisation überwachen können.</span><span class="sxs-lookup"><span data-stu-id="e6def-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="e6def-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im [Security & Compliance Center](https://office.protection.com) anzeigen, indem Sie zum **Reports** \> **Dashboard**Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="e6def-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e6def-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e6def-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="e6def-108">Connector-Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-108">Connector report</span></span>

<span data-ttu-id="e6def-109">Der **Bericht Connector** zeigt die Nachrichtenfluss Aktivität für die [eingehenden und ausgehenden Connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e6def-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="e6def-110">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **connectorbericht**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="e6def-111">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="e6def-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connector-Berichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="e6def-113">Berichtsansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-113">Report view for the Connector report</span></span>

<span data-ttu-id="e6def-114">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e6def-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="e6def-115">**Anzeigen von Daten nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, die von organisiert werden:</span><span class="sxs-lookup"><span data-stu-id="e6def-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="e6def-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="e6def-116">**Total**</span></span>
  - <span data-ttu-id="e6def-117">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e6def-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e6def-118">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e6def-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e6def-119">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="e6def-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="e6def-120">Um die Daten im Diagramm zu isolieren, verwenden Sie die Option **Daten für** SteuerelementAnzeigen, um eine dieser Optionen oder den **gesamten Nachrichtenfluss**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e6def-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach dem Nachrichtenfluss im connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="e6def-122">**Daten nach: TLS Usage**: in diesem Diagramm wird der prozentuale Anteil der TLS-Version (Transport Layer Security) für den Nachrichtenfluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="e6def-123">Um die Daten im Diagramm zu isolieren, wählen Sie mithilfe des Steuerelements **Daten anzeigen für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e6def-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="e6def-124">**Gesamter Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="e6def-124">**All mail flow**</span></span>
  - <span data-ttu-id="e6def-125">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e6def-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e6def-126">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="e6def-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e6def-127">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="e6def-127">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="e6def-129">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="e6def-130">Detailtabellen Ansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-130">Details table view for the Connector report</span></span>

<span data-ttu-id="e6def-131">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6def-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e6def-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6def-132">**Date**</span></span>
- <span data-ttu-id="e6def-133">**Verbindungsrichtung und-Name**</span><span class="sxs-lookup"><span data-stu-id="e6def-133">**Connector direction and name**</span></span>
- <span data-ttu-id="e6def-134">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="e6def-134">**Connector type**</span></span>
- <span data-ttu-id="e6def-135">**Forced TLS?**: der Wert **true** oder **false**.</span><span class="sxs-lookup"><span data-stu-id="e6def-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="e6def-136">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e6def-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="e6def-137">**TLS 1,0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e6def-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="e6def-138">**TLS 1,1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e6def-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="e6def-139">**TLS 1,2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="e6def-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="e6def-140">**Volume**: die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e6def-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="e6def-141">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6def-142">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="e6def-143">Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-143">Exchange transport rule report</span></span>

<span data-ttu-id="e6def-144">Der **Exchange-Transportregel Bericht** zeigt die Auswirkungen von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) auf ein-und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e6def-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="e6def-145">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Exchange-Transport Regel**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="e6def-146">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="e6def-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e6def-148">Berichtsansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="e6def-149">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e6def-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="e6def-150">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e6def-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="e6def-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Severity**: Dieses Diagramm zeigt die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem**Schweregrad sowie Nachrichten mit **niedrigem Schweregrad** .</span><span class="sxs-lookup"><span data-stu-id="e6def-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="e6def-152">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit schwere** Grad oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="e6def-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="e6def-153">Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="e6def-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="e6def-154">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von den DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e6def-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="e6def-155">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6def-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e6def-156">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="e6def-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e6def-157">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e6def-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e6def-158">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e6def-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="e6def-159">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: in dieser Ansicht wird die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem Schweregrad**sowie Nachrichten mit **niedrigem Schweregrad** angezeigt, die von den DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="e6def-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="e6def-160">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6def-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e6def-161">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="e6def-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e6def-162">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e6def-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e6def-163">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e6def-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="e6def-164">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e6def-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="e6def-165">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e6def-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="e6def-166">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e6def-166">Direction values</span></span>
- <span data-ttu-id="e6def-167">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="e6def-167">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregel Bericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e6def-169">Detailtabellen Ansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="e6def-170">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="e6def-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e6def-171">**Anzeigen von Daten nach: Exchange-Transport Regeln**:</span><span class="sxs-lookup"><span data-stu-id="e6def-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="e6def-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6def-172">**Date**</span></span>
  - <span data-ttu-id="e6def-173">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="e6def-173">**Transport rule**</span></span>
  - <span data-ttu-id="e6def-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="e6def-174">**Subject**</span></span>
  - <span data-ttu-id="e6def-175">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="e6def-175">**Sender address**</span></span>
  - <span data-ttu-id="e6def-176">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="e6def-176">**Recipient address**</span></span>
  - <span data-ttu-id="e6def-177">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="e6def-177">**Severity**</span></span>
  - <span data-ttu-id="e6def-178">**Direction**</span><span class="sxs-lookup"><span data-stu-id="e6def-178">**Direction**</span></span>

- <span data-ttu-id="e6def-179">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="e6def-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="e6def-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6def-180">**Date**</span></span>
  - <span data-ttu-id="e6def-181">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="e6def-181">**DLP policy**</span></span>
  - <span data-ttu-id="e6def-182">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="e6def-182">**Transport rule**</span></span>
  - <span data-ttu-id="e6def-183">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="e6def-183">**Subject**</span></span>
  - <span data-ttu-id="e6def-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="e6def-184">**Sender address**</span></span>
  - <span data-ttu-id="e6def-185">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="e6def-185">**Recipient address**</span></span>
  - <span data-ttu-id="e6def-186">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="e6def-186">**Severity**</span></span>
  - <span data-ttu-id="e6def-187">**Direction**</span><span class="sxs-lookup"><span data-stu-id="e6def-187">**Direction**</span></span>

<span data-ttu-id="e6def-188">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e6def-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e6def-189">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e6def-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="e6def-190">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e6def-190">Direction values</span></span>
- <span data-ttu-id="e6def-191">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="e6def-191">Severity values</span></span>

<span data-ttu-id="e6def-192">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="e6def-193">Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-193">Forwarding report</span></span>

<span data-ttu-id="e6def-194">Der **Weiterleitungs Bericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="e6def-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="e6def-195">Weitergeleitete Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf ein kompromittiertes Konto hindeuten.</span><span class="sxs-lookup"><span data-stu-id="e6def-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="e6def-196">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **weiter Leitungs Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="e6def-197">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="e6def-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleiten des Berichts-Widgets im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="e6def-199">Berichtsansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="e6def-200">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e6def-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e6def-201">**Daten anzeigen für: Weiterleitungs Methoden**: die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6def-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="e6def-202">**Transport Regel**: auch als [Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e6def-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="e6def-203">**Postfachregel**: auch [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)genannt.</span><span class="sxs-lookup"><span data-stu-id="e6def-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungs Methoden" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="e6def-205">**Daten anzeigen für: Forwarding Domains**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung darstellen.</span><span class="sxs-lookup"><span data-stu-id="e6def-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleiten von Domänen" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="e6def-207">**Daten anzeigen für: Forwarder**: die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6def-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="e6def-208">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="e6def-208">**Transport rule**</span></span>
  - <span data-ttu-id="e6def-209">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="e6def-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarder-Ansicht im Weiterleitungs Bericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="e6def-211">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="e6def-212">Detailtabellen Ansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="e6def-213">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6def-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e6def-214">**Weiterleitungen**: die Wert **Transport Regel** oder das Postfach, das die Posteingangsregel "Weiterleiten" enthält.</span><span class="sxs-lookup"><span data-stu-id="e6def-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="e6def-215">**Weiterleitungs**: der Wert für die **Postfachregel** oder die **Transport Regel**.</span><span class="sxs-lookup"><span data-stu-id="e6def-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="e6def-216">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="e6def-216">**Recipient name**</span></span>
- <span data-ttu-id="e6def-217">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="e6def-217">**Recipient domain**</span></span>
- <span data-ttu-id="e6def-218">**Details**: Dies ist der GUID-Wert der Nachrichtenfluss Regel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="e6def-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="e6def-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-219">**Count**</span></span>
- <span data-ttu-id="e6def-220">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="e6def-220">**First forward date**</span></span>

<span data-ttu-id="e6def-221">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6def-222">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e6def-223">Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-223">Mailflow status report</span></span>

<span data-ttu-id="e6def-224">Der **Nachrichtenfluss-Statusbericht** ähnelt dem [gesendeten und empfangenen e-Mail-Bericht](#sent-and-received-email-report), wobei zusätzliche Informationen zu e-Mail-Nachrichten zugelassen oder am Edge blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6def-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="e6def-225">Dies ist der einzige Bericht, der Informationen zum Edge-Schutz enthält, und zeigt, wie viele e-Mails blockiert werden, bevor Sie in den Dienst zur Evaluierung durch Exchange Online Protection (EoP) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="e6def-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e6def-226">Es ist wichtig zu verstehen, dass wenn eine Nachricht an fünf Empfänger gesendet wird, wir Sie als fünf verschiedene Nachrichten und nicht eine Nachricht zählen.</span><span class="sxs-lookup"><span data-stu-id="e6def-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="e6def-227">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Nachrichtenflussstatus Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="e6def-228">Wenn Sie direkt zum **Nachrichtenflussstatus Bericht**wechseln möchten, öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="e6def-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenfluss-Statusbericht-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="e6def-230">Typansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="e6def-231">Wenn Sie den Bericht öffnen, ist die Registerkarte **Typ** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e6def-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="e6def-232">Diese Ansicht enthält standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e6def-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e6def-233">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e6def-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="e6def-234">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="e6def-234">**Direction**:</span></span>

  - <span data-ttu-id="e6def-235">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-235">**Inbound**</span></span>
  - <span data-ttu-id="e6def-236">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-236">**Outbound**</span></span>
  - <span data-ttu-id="e6def-237">**Intra-org**: diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="e6def-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e6def-238">Absender ABC@Domain.com wird an den Empfänger XYZ@Domain.com gesendet (separat **Inbound** von eingehend **und**ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="e6def-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="e6def-239">**Geben**Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e6def-239">**Type**:</span></span>

  - <span data-ttu-id="e6def-240">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="e6def-240">**Good mail**</span></span>
  - <span data-ttu-id="e6def-241">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="e6def-241">**Malware**</span></span>
  - <span data-ttu-id="e6def-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="e6def-242">**Spam**</span></span>
  - <span data-ttu-id="e6def-243">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="e6def-243">**Edge protection**</span></span>
  - <span data-ttu-id="e6def-244">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="e6def-244">**Rule messages**</span></span>
  - <span data-ttu-id="e6def-245">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e6def-245">**Phishing email**</span></span>

<span data-ttu-id="e6def-246">Das Diagramm wird nach den **Typwerten** sortiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="e6def-247">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="e6def-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="e6def-248">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e6def-248">The data table contains the following information:</span></span>

- <span data-ttu-id="e6def-249">**Direction**</span><span class="sxs-lookup"><span data-stu-id="e6def-249">**Direction**</span></span>
- <span data-ttu-id="e6def-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6def-250">**Type**</span></span>
- <span data-ttu-id="e6def-251">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="e6def-251">**24 hours**</span></span>
- <span data-ttu-id="e6def-252">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="e6def-252">**3 days**</span></span>
- <span data-ttu-id="e6def-253">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="e6def-253">**7 days**</span></span>
- <span data-ttu-id="e6def-254">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="e6def-254">**15 days**</span></span>
- <span data-ttu-id="e6def-255">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="e6def-255">**30 days**</span></span>

<span data-ttu-id="e6def-256">Wenn Sie auf **Kategorie auswählen klicken, um weitere Informationen zu**erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6def-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="e6def-257">**Phishing-e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e6def-258">**Schadsoftware in e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e6def-259">**Spamerkennungen**: Diese Auswahl führt Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="e6def-260">**Spam blockierter Edge**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e6def-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e6def-261">**Export**:</span></span>

<span data-ttu-id="e6def-262">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="e6def-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e6def-263">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="e6def-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e6def-264">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e6def-265">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6def-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e6def-266">Typansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="e6def-267">Richtungs Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="e6def-268">Wenn Sie auf die Registerkarte **Richtung** klicken, werden die gleichen Standardfilter aus der **Typansicht verwendet** .</span><span class="sxs-lookup"><span data-stu-id="e6def-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="e6def-269">Das Diagramm ist nach **Richtungs** Werten angeordnet.</span><span class="sxs-lookup"><span data-stu-id="e6def-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="e6def-270">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="e6def-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="e6def-271">In der **Typansicht werden** dieselben Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6def-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="e6def-272">Die Datentabelle enthält dieselben Informationen aus der **Typen** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="e6def-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="e6def-273">Die **Kategorie Choose a category for More Details** available Selections and Behavior sind identisch mit der **Type** -Ansicht.</span><span class="sxs-lookup"><span data-stu-id="e6def-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="e6def-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e6def-274">**Export**:</span></span>

<span data-ttu-id="e6def-275">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="e6def-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e6def-276">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="e6def-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e6def-277">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e6def-278">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6def-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e6def-279">Richtungs Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="e6def-280">Trichter Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="e6def-281">In der **Trichter** Ansicht erfahren Sie, wie die e-Mail-Bedrohungsschutz Funktionen von Microsoft eingehende und ausgehende e-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="e6def-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="e6def-282">Es enthält Details zur Gesamtzahl der e-Mails und dazu, wie die konfigurierten Funktionen zum Schutz vor Bedrohungen, einschließlich Edgeschutz, Antischadsoftware, AntiPhishing, Antispam-und Antispoofing diese Anzahl beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="e6def-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="e6def-283">Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e6def-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e6def-284">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e6def-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e6def-285">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="e6def-285">**Direction**:</span></span>

  - <span data-ttu-id="e6def-286">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-286">**Inbound**</span></span>
  - <span data-ttu-id="e6def-287">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-287">**Outbound**</span></span>
  - <span data-ttu-id="e6def-288">**Intra-org**: diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; Das heißt, Absender-ABC@Domain.com sendet an den Empfänger XYZ@Domain.com (separat von eingehend und ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="e6def-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="e6def-289">Die Ansicht aggregierte Ansicht und Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e6def-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e6def-290">Wenn Sie auf **Filter**klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="e6def-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e6def-291">Dieses Diagramm zeigt die Anzahl der e-Mail-Nachweise:</span><span class="sxs-lookup"><span data-stu-id="e6def-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="e6def-292">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="e6def-292">**Total email**</span></span>
- <span data-ttu-id="e6def-293">**E-Mail nach dem Edge-Schutz**</span><span class="sxs-lookup"><span data-stu-id="e6def-293">**Email after edge protection**</span></span>
- <span data-ttu-id="e6def-294">**E-Mail nach Anti-Malware, Datei Zuverlässigkeit, Dateityp Block**</span><span class="sxs-lookup"><span data-stu-id="e6def-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="e6def-295">**E-Mail nach Anti-Phishing, URL-Reputation, Marken Identitätswechsel, Anti-Spoofing**</span><span class="sxs-lookup"><span data-stu-id="e6def-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="e6def-296">**E-Mail nach Spam Schutz, Massen-e-Mail-Filterung**</span><span class="sxs-lookup"><span data-stu-id="e6def-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="e6def-297">**E-Mail nach Benutzer-und Domänen Identitätswechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6def-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="e6def-298">**E-Mail nach Datei-und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6def-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="e6def-299">**E-Mail-Nachricht wurde nach dem Zustellungs Schutz als gutartig erkannt (URL-Klick-Zeit Schutz)**</span><span class="sxs-lookup"><span data-stu-id="e6def-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="e6def-300"><sup>1</sup> Office 365 nur ATP</span><span class="sxs-lookup"><span data-stu-id="e6def-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="e6def-301">Wenn Sie die von EoP oder ATP gefilterte e-Mail separat anzeigen möchten, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="e6def-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="e6def-302">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e6def-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e6def-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6def-303">**Date**</span></span>
- <span data-ttu-id="e6def-304">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="e6def-304">**Total email**</span></span>
- <span data-ttu-id="e6def-305">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="e6def-305">**Edge protection**</span></span> 
- <span data-ttu-id="e6def-306">**Anti-Malware, Datei Zuverlässigkeit, Dateityp Block**:</span><span class="sxs-lookup"><span data-stu-id="e6def-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="e6def-307">**Dateireputation**: Nachrichten, die aufgrund der Identifizierung einer angehängten Datei durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="e6def-308">**Dateityp Block**: Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>      
- <span data-ttu-id="e6def-309">**Anti-Phishing, URL-Reputation, Marken Identitätswechsel, Spoofing**:</span><span class="sxs-lookup"><span data-stu-id="e6def-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="e6def-310">**URL-Reputation**: Nachrichten, die aufgrund der Identifizierung der URL durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="e6def-311">**Marken Identitätswechsel**: Nachrichten, die aufgrund der Nachricht aus bekannten Absender der Markenidentität gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="e6def-312">**Anti-Spoof**: Nachrichten, die aufgrund der Nachricht gefiltert werden, die versucht, eine Domäne zu fälschen, zu der der Empfänger gehört, oder eine Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="e6def-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>  
- <span data-ttu-id="e6def-313">**Anti-Spam, Massen-e-Mail-Filterung**:</span><span class="sxs-lookup"><span data-stu-id="e6def-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="e6def-314">**Massen-e-Mail-Filterung**: Nachrichten, die aufgrund eines Versuchs zur Zustellung von Massen-e-Mails an die Empfänger gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span> 
- <span data-ttu-id="e6def-315">**Benutzer-und Domänen Identitätswechsel (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="e6def-315">**User and domain impersonation (ATP)**:</span></span>
  - <span data-ttu-id="e6def-316">**Benutzeridentitätswechsel**: Nachrichten, die aufgrund eines Versuchs zur Identitätswechsel eines Benutzers (Nachrichtenabsender) gefiltert wurden, der in den Identitätswechsel-Schutzeinstellungen einer Anti-Phishing-Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e6def-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="e6def-317">**Domänen Identitätswechsel**: Nachrichten, die aufgrund eines Versuchs zur Identitätswechsel einer Domäne gefiltert wurden, die in den Identitätswechsel-Schutzeinstellungen einer Anti-Phishing-Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e6def-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span> 
- <span data-ttu-id="e6def-318">**Datei-und URL-Detonation (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="e6def-318">**File and URL detonation (ATP)**:</span></span>
  - <span data-ttu-id="e6def-319">**Datei Explosion**: Nachrichten, die von einer Richtlinie für sichere Anlagen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="e6def-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="e6def-320">**URL-Detonation**: Nachricht, gefiltert nach einer Richtlinie zu sicheren Links.</span><span class="sxs-lookup"><span data-stu-id="e6def-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>  
- <span data-ttu-id="e6def-321">**Schutz nach Zustellung und zap (ATP) oder zap (EoP)**: Zap gibt die automatische Bereinigung der Nullstunde an.</span><span class="sxs-lookup"><span data-stu-id="e6def-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="e6def-322">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der e-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e6def-323">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e6def-323">**Export**:</span></span>

<span data-ttu-id="e6def-324">Nachdem Sie unter **Optionen**auf **exportieren** klicken, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6def-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="e6def-325">**Zusammenfassung (höchstens mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e6def-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e6def-326">**Details (höchstens mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e6def-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e6def-327">Wählen Sie unter **Datum**einen Bereich aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="e6def-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e6def-328">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e6def-329">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e6def-330">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6def-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e6def-331">Trichter Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="e6def-332">Tech-Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="e6def-333">Die **Tech-Ansicht** ähnelt der **Trichter** Ansicht und bietet detailliertere Details für die konfigurierten Features zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="e6def-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="e6def-334">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Stadien des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6def-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="e6def-335">Wenn Sie auf die Registerkarte **Tech-Ansicht** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e6def-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e6def-336">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="e6def-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e6def-337">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="e6def-337">**Direction**:</span></span>

  - <span data-ttu-id="e6def-338">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-338">**Inbound**</span></span>
  - <span data-ttu-id="e6def-339">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="e6def-339">**Outbound**</span></span>
  - <span data-ttu-id="e6def-340">**Intra-org**: diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="e6def-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e6def-341">Absender ABC@Domain.com wird an den Empfänger XYZ@Domain.com gesendet (separat von eingehend und ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="e6def-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="e6def-342">Die Ansicht aggregierte Ansicht und Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e6def-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e6def-343">Wenn Sie auf **Filter**klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="e6def-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e6def-344">In diesem Diagramm werden Nachrichten angezeigt, die in die folgenden Kategorien aufgeteilt sind:</span><span class="sxs-lookup"><span data-stu-id="e6def-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="e6def-345">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="e6def-345">**Total email**</span></span>
- <span data-ttu-id="e6def-346">**Edge-allow, Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="e6def-346">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="e6def-347">**Nicht Schadsoftware, Erkennung sicherer Anlagen (ATP), Erkennung von Anti-Malware-Engines, Regelblock**</span><span class="sxs-lookup"><span data-stu-id="e6def-347">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="e6def-348">**Nicht Phishing, DMARC-Fehler, Identitätswechsel Erkennung, spoof-Erkennung, Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="e6def-348">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="e6def-349">**Keine Erkennung mit URL-Detonation, URL-detonations Erkennung (ATP)**</span><span class="sxs-lookup"><span data-stu-id="e6def-349">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="e6def-350">**Kein Spam, Spam**</span><span class="sxs-lookup"><span data-stu-id="e6def-350">**Not spam, spam**</span></span>
- <span data-ttu-id="e6def-351">**Nicht-böswillige e-Mails, Erkennung von sicheren Links (ATP), Zap**</span><span class="sxs-lookup"><span data-stu-id="e6def-351">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="e6def-352">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-352">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="e6def-353">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e6def-353">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e6def-354">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6def-354">**Date**</span></span>
- <span data-ttu-id="e6def-355">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="e6def-355">**Total email**</span></span>
- <span data-ttu-id="e6def-356">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="e6def-356">**Edge filtered**</span></span>
- <span data-ttu-id="e6def-357">**Anti-Malware-Modul, sichere Anlagen, Regelfilter**:</span><span class="sxs-lookup"><span data-stu-id="e6def-357">**Anti-malware engine, safe attachments, rule filtered**:</span></span>
  - <span data-ttu-id="e6def-358">**Regel gefiltert**: Nachrichten, die aufgrund von Nachrichtenfluss Regeln gefiltert wurden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="e6def-358">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="e6def-359">**DMARC, Identitätswechsel, Spoofing, Phishing-Filterung**:</span><span class="sxs-lookup"><span data-stu-id="e6def-359">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="e6def-360">**DMARC**: Nachrichten, die aufgrund der Nachricht, deren DMARC-Authentifizierungsüberprüfung fehlgeschlagen ist, gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6def-360">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span> 
- <span data-ttu-id="e6def-361">**URL-detonations Erkennung**</span><span class="sxs-lookup"><span data-stu-id="e6def-361">**URL detonation detection**</span></span>
- <span data-ttu-id="e6def-362">**Anti-Spam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="e6def-362">**Anti-spam filtered**</span></span>
- <span data-ttu-id="e6def-363">**Zap entfernt**</span><span class="sxs-lookup"><span data-stu-id="e6def-363">**ZAP removed**</span></span>
- <span data-ttu-id="e6def-364">**Erkennung durch sichere Links**</span><span class="sxs-lookup"><span data-stu-id="e6def-364">**Detection by safe links**</span></span>

<span data-ttu-id="e6def-365">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der e-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-365">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e6def-366">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e6def-366">**Export**:</span></span>

<span data-ttu-id="e6def-367">Beim Klicken auf **exportieren**unter **Optionen** können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6def-367">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="e6def-368">**Zusammenfassung (höchstens mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e6def-368">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e6def-369">**Details (höchstens mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="e6def-369">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e6def-370">Wählen Sie unter **Datum**einen Bereich aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="e6def-370">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e6def-371">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-371">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e6def-372">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="e6def-372">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e6def-373">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6def-373">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e6def-374">Tech-Ansicht im Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-374">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e6def-375">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="e6def-375">Sent and received email report</span></span>

<span data-ttu-id="e6def-376">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="e6def-376">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="e6def-377">Der Unterschied zwischen diesem Bericht und dem Nachrichten [Fluss Statusbericht](#mailflow-status-report) lautet: dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edge-Schutz blockiert wurden. Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="e6def-377">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="e6def-378">Die Aggregatansicht und die Detailansicht des Berichts erlauben eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e6def-378">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="e6def-379">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **gesendete und empfangene e-Mails**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-379">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="e6def-380">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="e6def-380">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendete und empfangene e-Mail-widget im Dashboard Berichte](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e6def-382">Berichtsansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-382">Report view for the Sent and received email report</span></span>

<span data-ttu-id="e6def-383">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e6def-383">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e6def-384">**Aufschlüsseln nach: Typ**: das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="e6def-384">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="e6def-385">**Total**</span><span class="sxs-lookup"><span data-stu-id="e6def-385">**Total**</span></span>
  - <span data-ttu-id="e6def-386">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="e6def-386">**Good mail**</span></span>
  - <span data-ttu-id="e6def-387">**Schadsoftware (Anti-Malware)** (EoP)</span><span class="sxs-lookup"><span data-stu-id="e6def-387">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="e6def-388">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="e6def-388">**Spam detections**</span></span>
  - <span data-ttu-id="e6def-389">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="e6def-389">**Rule messages**</span></span>
  - <span data-ttu-id="e6def-390">**Erweiterte Schadsoftware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="e6def-390">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="e6def-391">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-391">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Geben Sie Ansicht im Bericht gesendete und empfangene e-Mails ein.](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="e6def-393">**Aufschlüsseln nach: Direction**: das Diagramm zeigt **Gesamt**-, **eingehende**und **ausgehende** Daten.</span><span class="sxs-lookup"><span data-stu-id="e6def-393">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="e6def-394">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-394">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungs Ansicht im Bericht "gesendete und empfangene e-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="e6def-396">**Drilldown nach** \> **Schadsoftware (Anti-Malware)**: mit dieser Auswahl gelangen Sie zur [Malware Erkennung in e-Mail-Bericht](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-396">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="e6def-397">**Drilldown nach** \> **Spamerkennungen)**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="e6def-397">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e6def-398">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e6def-398">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e6def-399">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e6def-399">**Start date** and **End date**</span></span>
- <span data-ttu-id="e6def-400">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e6def-400">Direction values</span></span>
- <span data-ttu-id="e6def-401">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="e6def-401">Type values</span></span>

<span data-ttu-id="e6def-402">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-402">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e6def-403">Detailtabellen Ansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="e6def-403">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="e6def-404">Wenn Sie auf **Tabelle Details anzeigen** in der Ansicht **aufschlüsseln nach: Richtung** oder **aufschlüsseln nach: Richtungs** Ansicht klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6def-404">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="e6def-405">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="e6def-405">**Date (UTC)**</span></span>
- <span data-ttu-id="e6def-406">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6def-406">**Type**</span></span>
- <span data-ttu-id="e6def-407">**Direction**</span><span class="sxs-lookup"><span data-stu-id="e6def-407">**Direction**</span></span>
- <span data-ttu-id="e6def-408">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e6def-408">**Message count**</span></span>

<span data-ttu-id="e6def-409">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="e6def-409">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e6def-410">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="e6def-410">**Start date** and **End date**</span></span>
- <span data-ttu-id="e6def-411">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="e6def-411">Direction values</span></span>
- <span data-ttu-id="e6def-412">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="e6def-412">Type values</span></span>

<span data-ttu-id="e6def-413">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-413">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e6def-414">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="e6def-414">Top senders and recipients report</span></span>

<span data-ttu-id="e6def-415">Der Bericht " **oberster Absender und Empfänger** " ist ein Kreisdiagramm, in dem Ihre oberen e-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6def-415">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="e6def-416">Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **oberste Absender und Empfänger**aus.</span><span class="sxs-lookup"><span data-stu-id="e6def-416">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="e6def-417">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="e6def-417">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Top-Absender und Empfänger-Widget im Dashboard Berichte](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e6def-419">Berichtsansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-419">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="e6def-420">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e6def-420">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e6def-421">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e6def-421">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="e6def-422">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-422">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="e6def-423">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-423">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="e6def-424">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="e6def-424">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="e6def-425">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="e6def-425">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="e6def-426">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="e6def-426">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="e6def-427">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6def-427">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="e6def-428">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-428">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "obere Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e6def-430">Detailtabellen Ansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="e6def-430">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="e6def-431">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="e6def-431">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e6def-432">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e6def-432">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="e6def-433">**Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="e6def-433">**Top mail senders**</span></span>
  - <span data-ttu-id="e6def-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-434">**Count**</span></span>

- <span data-ttu-id="e6def-435">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-435">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="e6def-436">**Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-436">**Top mail recipients**</span></span>
  - <span data-ttu-id="e6def-437">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-437">**Count**</span></span>

- <span data-ttu-id="e6def-438">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-438">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="e6def-439">**Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-439">**Top spam recipients**</span></span>
  - <span data-ttu-id="e6def-440">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-440">**Count**</span></span>

- <span data-ttu-id="e6def-441">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="e6def-441">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="e6def-442">**Top-Schadsoftware-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="e6def-442">**Top malware recipients**</span></span>
  - <span data-ttu-id="e6def-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-443">**Count**</span></span>

- <span data-ttu-id="e6def-444">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="e6def-444">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="e6def-445">**Top-Malware Empfänger (ATP)**</span><span class="sxs-lookup"><span data-stu-id="e6def-445">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="e6def-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6def-446">**Count**</span></span>

<span data-ttu-id="e6def-447">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="e6def-447">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6def-448">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e6def-448">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e6def-449">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="e6def-449">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e6def-450">Zum Anzeigen und Verwenden der Berichte müssen Sie Mitglied der angegebenen Rollengruppe im Security & Compliance Center **und** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="e6def-450">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="e6def-451">Im Security & Compliance Center müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="e6def-451">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e6def-452">-Organisationsverwaltung-Sicherheits Administrator (Dies können Sie auch im [Azure Active Directory Admin Center](https://aad.portal.azure.com) – Sicherheits Leser</span><span class="sxs-lookup"><span data-stu-id="e6def-452">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="e6def-453">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="e6def-453">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="e6def-454">In Exchange Online müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="e6def-454">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e6def-455">-Organisationsverwaltung-nur Ansichts Organisationsverwaltung-nur Empfänger – Compliance-Management</span><span class="sxs-lookup"><span data-stu-id="e6def-455">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="e6def-456">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="e6def-456">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6def-457">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e6def-457">Related topics</span></span>

[<span data-ttu-id="e6def-458">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e6def-458">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e6def-459">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e6def-459">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="e6def-460">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e6def-460">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e6def-461">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e6def-461">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
