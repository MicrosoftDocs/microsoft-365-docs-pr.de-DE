---
title: Nachrichtenfluss-Einblicke im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie Nachrichtenfluss-Sicherheitsberichte für Ihre Organisation suchen und verwenden. Nachrichtenfluss Berichte sind im Security & Compliance Center verfügbar.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434179"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="f9fcc-104">Nachrichtenfluss-Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f9fcc-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="f9fcc-105">Zusätzlich zu den [Nachrichtenfluss Einblicken](mail-flow-insights-v2.md) , die im Security & Compliance Center zur Verfügung stehen, stehen Ihnen auch eine Vielzahl von Nachrichtenfluss Berichten zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="f9fcc-106">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & Compliance Center unter <https://office.protection.com> mit dem Dashboard " **Berichte** " anzeigen \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f9fcc-107">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="f9fcc-109">Connector-Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-109">Connector report</span></span>

<span data-ttu-id="f9fcc-110">Der **Bericht Connector** zeigt die Nachrichtenfluss Aktivität für die [eingehenden und ausgehenden Connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="f9fcc-111">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **connectorbericht**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="f9fcc-112">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connector-Berichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="f9fcc-114">Berichtsansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-114">Report view for the Connector report</span></span>

<span data-ttu-id="f9fcc-115">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9fcc-116">**Anzeigen von Daten nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, die von organisiert werden:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="f9fcc-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-117">**Total**</span></span>
  - <span data-ttu-id="f9fcc-118">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9fcc-119">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9fcc-120">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="f9fcc-121">Um die Daten im Diagramm zu isolieren, verwenden Sie die Option **Daten für** SteuerelementAnzeigen, um eine dieser Optionen oder den **gesamten Nachrichtenfluss**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach dem Nachrichtenfluss im connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="f9fcc-123">**Daten nach: TLS Usage**: in diesem Diagramm wird der prozentuale Anteil der TLS-Version (Transport Layer Security) für den Nachrichtenfluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="f9fcc-124">Um die Daten im Diagramm zu isolieren, wählen Sie mithilfe des Steuerelements **Daten anzeigen für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="f9fcc-125">**Gesamter Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-125">**All mail flow**</span></span>
  - <span data-ttu-id="f9fcc-126">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9fcc-127">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9fcc-128">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-128">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="f9fcc-130">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="f9fcc-131">Detailtabellen Ansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-131">Details table view for the Connector report</span></span>

<span data-ttu-id="f9fcc-132">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9fcc-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-133">**Date**</span></span>
- <span data-ttu-id="f9fcc-134">**Verbindungsrichtung und-Name**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-134">**Connector direction and name**</span></span>
- <span data-ttu-id="f9fcc-135">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-135">**Connector type**</span></span>
- <span data-ttu-id="f9fcc-136">**Forced TLS?**: der Wert **true** oder **false**.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="f9fcc-137">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="f9fcc-138">**TLS 1,0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="f9fcc-139">**TLS 1,1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="f9fcc-140">**TLS 1,2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="f9fcc-141">**Volume**: die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="f9fcc-142">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9fcc-143">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f9fcc-144">Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-144">Exchange transport rule report</span></span>

<span data-ttu-id="f9fcc-145">Der **Exchange-Transportregel Bericht** zeigt die Auswirkungen von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) auf ein-und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f9fcc-146">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Exchange-Transport Regel**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="f9fcc-147">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9fcc-149">Berichtsansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9fcc-150">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9fcc-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="f9fcc-152">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Severity**: Dieses Diagramm zeigt die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem**Schweregrad sowie Nachrichten mit **niedrigem Schweregrad** .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f9fcc-153">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit schwere** Grad oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f9fcc-154">Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f9fcc-155">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von den DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="f9fcc-156">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9fcc-157">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9fcc-158">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9fcc-159">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="f9fcc-160">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: in dieser Ansicht wird die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem Schweregrad**sowie Nachrichten mit **niedrigem Schweregrad** angezeigt, die von den DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="f9fcc-161">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9fcc-162">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9fcc-163">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9fcc-164">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="f9fcc-165">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="f9fcc-166">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9fcc-167">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-167">Direction values</span></span>
- <span data-ttu-id="f9fcc-168">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-168">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregel Bericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9fcc-170">Detailtabellen Ansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9fcc-171">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9fcc-172">**Anzeigen von Daten nach: Exchange-Transport Regeln**:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="f9fcc-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-173">**Date**</span></span>
  - <span data-ttu-id="f9fcc-174">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-174">**Transport rule**</span></span>
  - <span data-ttu-id="f9fcc-175">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-175">**Subject**</span></span>
  - <span data-ttu-id="f9fcc-176">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-176">**Sender address**</span></span>
  - <span data-ttu-id="f9fcc-177">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-177">**Recipient address**</span></span>
  - <span data-ttu-id="f9fcc-178">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-178">**Severity**</span></span>
  - <span data-ttu-id="f9fcc-179">**Direction**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-179">**Direction**</span></span>

- <span data-ttu-id="f9fcc-180">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="f9fcc-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-181">**Date**</span></span>
  - <span data-ttu-id="f9fcc-182">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-182">**DLP policy**</span></span>
  - <span data-ttu-id="f9fcc-183">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-183">**Transport rule**</span></span>
  - <span data-ttu-id="f9fcc-184">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-184">**Subject**</span></span>
  - <span data-ttu-id="f9fcc-185">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-185">**Sender address**</span></span>
  - <span data-ttu-id="f9fcc-186">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-186">**Recipient address**</span></span>
  - <span data-ttu-id="f9fcc-187">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-187">**Severity**</span></span>
  - <span data-ttu-id="f9fcc-188">**Direction**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-188">**Direction**</span></span>

<span data-ttu-id="f9fcc-189">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9fcc-190">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9fcc-191">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-191">Direction values</span></span>
- <span data-ttu-id="f9fcc-192">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-192">Severity values</span></span>

<span data-ttu-id="f9fcc-193">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f9fcc-194">Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-194">Forwarding report</span></span>

<span data-ttu-id="f9fcc-195">Der **Weiterleitungs Bericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="f9fcc-196">Weitergeleitete Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf ein kompromittiertes Konto hindeuten.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="f9fcc-197">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **weiter Leitungs Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="f9fcc-198">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleiten des Berichts-Widgets im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="f9fcc-200">Berichtsansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="f9fcc-201">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9fcc-202">**Daten anzeigen für: Weiterleitungs Methoden**: die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="f9fcc-203">**Transport Regel**: auch als [Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="f9fcc-204">**Postfachregel**: auch [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)genannt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungs Methoden" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="f9fcc-206">**Daten anzeigen für: Forwarding Domains**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung darstellen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleiten von Domänen" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="f9fcc-208">**Daten anzeigen für: Forwarder**: die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="f9fcc-209">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-209">**Transport rule**</span></span>
  - <span data-ttu-id="f9fcc-210">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarder-Ansicht im Weiterleitungs Bericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="f9fcc-212">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="f9fcc-213">Detailtabellen Ansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="f9fcc-214">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9fcc-215">**Weiterleitungen**: die Wert **Transport Regel** oder das Postfach, das die Posteingangsregel "Weiterleiten" enthält.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="f9fcc-216">**Weiterleitungs**: der Wert für die **Postfachregel** oder die **Transport Regel**.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="f9fcc-217">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-217">**Recipient name**</span></span>
- <span data-ttu-id="f9fcc-218">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-218">**Recipient domain**</span></span>
- <span data-ttu-id="f9fcc-219">**Details**: Dies ist der GUID-Wert der Nachrichtenfluss Regel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="f9fcc-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-220">**Count**</span></span>
- <span data-ttu-id="f9fcc-221">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-221">**First forward date**</span></span>

<span data-ttu-id="f9fcc-222">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9fcc-223">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f9fcc-224">Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-224">Mailflow status report</span></span>

<span data-ttu-id="f9fcc-225">Der **Nachrichtenfluss-Statusbericht** ähnelt dem [gesendeten und empfangenen e-Mail-Bericht](#sent-and-received-email-report), wobei zusätzliche Informationen zu e-Mail-Nachrichten zugelassen oder am Edge blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f9fcc-226">Dies ist der einzige Bericht, der Informationen zum Edge-Schutz enthält, und zeigt, wie viele e-Mails blockiert werden, bevor Sie in den Dienst zur Evaluierung durch Exchange Online Protection (EoP) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="f9fcc-227">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Nachrichtenflussstatus Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="f9fcc-228">Wenn Sie direkt zum **Nachrichtenflussstatus Bericht**wechseln möchten, öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenfluss-Statusbericht-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9fcc-230">Typansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f9fcc-231">Wenn Sie den Bericht öffnen, ist die Registerkarte **Typ** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f9fcc-232">Diese Ansicht enthält standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9fcc-233">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="f9fcc-234">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-234">**Direction**:</span></span>

  - <span data-ttu-id="f9fcc-235">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-235">**Inbound**</span></span>
  - <span data-ttu-id="f9fcc-236">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-236">**Outbound**</span></span>
  - <span data-ttu-id="f9fcc-237">**Intra-org** (wird getrennt von einem **eingehenden** und **ausgehenden**gezählt)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="f9fcc-238">**Geben**Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-238">**Type**:</span></span>

  - <span data-ttu-id="f9fcc-239">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-239">**Good mail**</span></span>
  - <span data-ttu-id="f9fcc-240">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-240">**Malware**</span></span>
  - <span data-ttu-id="f9fcc-241">**Spam**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-241">**Spam**</span></span>
  - <span data-ttu-id="f9fcc-242">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-242">**Edge protection**</span></span>
  - <span data-ttu-id="f9fcc-243">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-243">**Rule messages**</span></span>
  - <span data-ttu-id="f9fcc-244">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-244">**Phishing email**</span></span>

<span data-ttu-id="f9fcc-245">Das Diagramm wird nach den **Typwerten** sortiert.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f9fcc-246">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f9fcc-247">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-247">The data table contains the following information:</span></span>

- <span data-ttu-id="f9fcc-248">**Direction**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-248">**Direction**</span></span>
- <span data-ttu-id="f9fcc-249">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-249">**Type**</span></span>
- <span data-ttu-id="f9fcc-250">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-250">**24 hours**</span></span>
- <span data-ttu-id="f9fcc-251">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-251">**3 days**</span></span>
- <span data-ttu-id="f9fcc-252">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-252">**7 days**</span></span>
- <span data-ttu-id="f9fcc-253">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-253">**15 days**</span></span>
- <span data-ttu-id="f9fcc-254">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-254">**30 days**</span></span>

<span data-ttu-id="f9fcc-255">Wenn Sie auf **Kategorie auswählen klicken, um weitere Informationen zu**erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f9fcc-256">**Phishing-e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9fcc-257">**Schadsoftware in e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9fcc-258">**Spamerkennungen**: Diese Auswahl führt Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f9fcc-259">**Spam blockierter Edge**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9fcc-260">**Export**:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-260">**Export**:</span></span>

<span data-ttu-id="f9fcc-261">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9fcc-262">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9fcc-263">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9fcc-264">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f9fcc-265">Typansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9fcc-266">Richtungs Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f9fcc-267">Wenn Sie auf die Registerkarte **Richtung** klicken, werden die gleichen Standardfilter aus der **Typansicht verwendet** .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9fcc-268">Das Diagramm ist nach **Richtungs** Werten angeordnet.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f9fcc-269">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="f9fcc-270">In der **Typansicht werden** dieselben Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9fcc-271">Die Datentabelle enthält dieselben Informationen aus der **Typen** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f9fcc-272">Die **Kategorie Choose a category for More Details** available Selections and Behavior sind identisch mit der **Type** -Ansicht.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="f9fcc-273">**Export**:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-273">**Export**:</span></span>

<span data-ttu-id="f9fcc-274">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9fcc-275">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9fcc-276">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9fcc-277">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f9fcc-278">Richtungs Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f9fcc-279">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-279">Sent and received email report</span></span>

<span data-ttu-id="f9fcc-280">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="f9fcc-281">Der Unterschied zwischen diesem Bericht und dem Nachrichten [Fluss Statusbericht](#mailflow-status-report) lautet: dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edge-Schutz blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="f9fcc-282">Die Aggregatansicht und die Detailansicht des Berichts erlauben eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9fcc-283">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **gesendete und empfangene e-Mails**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="f9fcc-284">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendete und empfangene e-Mail-widget im Dashboard Berichte](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9fcc-286">Berichtsansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="f9fcc-287">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9fcc-288">**Aufschlüsseln nach: Typ**: das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="f9fcc-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-289">**Total**</span></span>
  - <span data-ttu-id="f9fcc-290">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-290">**Good mail**</span></span>
  - <span data-ttu-id="f9fcc-291">**Schadsoftware (Anti-Malware)** (EoP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="f9fcc-292">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-292">**Spam detections**</span></span>
  - <span data-ttu-id="f9fcc-293">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-293">**Rule messages**</span></span>
  - <span data-ttu-id="f9fcc-294">**Erweiterte Schadsoftware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="f9fcc-295">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Geben Sie Ansicht im Bericht gesendete und empfangene e-Mails ein.](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="f9fcc-297">**Aufschlüsseln nach: Direction**: das Diagramm zeigt **Gesamt**-, **eingehende**und **ausgehende** Daten.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="f9fcc-298">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungs Ansicht im Bericht "gesendete und empfangene e-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="f9fcc-300">**Drilldown nach** \> **Schadsoftware (Anti-Malware)**: mit dieser Auswahl gelangen Sie zur [Malware Erkennung in e-Mail-Bericht](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="f9fcc-301">**Drilldown nach** \> **Spamerkennungen)**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9fcc-302">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9fcc-303">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9fcc-304">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-304">Direction values</span></span>
- <span data-ttu-id="f9fcc-305">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-305">Type values</span></span>

<span data-ttu-id="f9fcc-306">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9fcc-307">Detailtabellen Ansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="f9fcc-308">Wenn Sie auf **Tabelle Details anzeigen** in der Ansicht **aufschlüsseln nach: Richtung** oder **aufschlüsseln nach: Richtungs** Ansicht klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="f9fcc-309">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-309">**Date (UTC)**</span></span>
- <span data-ttu-id="f9fcc-310">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-310">**Type**</span></span>
- <span data-ttu-id="f9fcc-311">**Direction**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-311">**Direction**</span></span>
- <span data-ttu-id="f9fcc-312">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-312">**Message count**</span></span>

<span data-ttu-id="f9fcc-313">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9fcc-314">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9fcc-315">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-315">Direction values</span></span>
- <span data-ttu-id="f9fcc-316">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="f9fcc-316">Type values</span></span>

<span data-ttu-id="f9fcc-317">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f9fcc-318">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="f9fcc-318">Top senders and recipients report</span></span>

<span data-ttu-id="f9fcc-319">Der Bericht " **oberster Absender und Empfänger** " ist ein Kreisdiagramm, in dem Ihre oberen e-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="f9fcc-320">Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **oberste Absender und Empfänger**aus.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="f9fcc-321">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="f9fcc-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Top-Absender und Empfänger-Widget im Dashboard Berichte](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9fcc-323">Berichtsansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9fcc-324">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9fcc-325">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="f9fcc-326">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="f9fcc-327">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="f9fcc-328">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="f9fcc-329">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="f9fcc-330">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="f9fcc-331">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="f9fcc-332">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "obere Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9fcc-334">Detailtabellen Ansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="f9fcc-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9fcc-335">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9fcc-336">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="f9fcc-337">**Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-337">**Top mail senders**</span></span>
  - <span data-ttu-id="f9fcc-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-338">**Count**</span></span>

- <span data-ttu-id="f9fcc-339">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="f9fcc-340">**Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="f9fcc-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-341">**Count**</span></span>

- <span data-ttu-id="f9fcc-342">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="f9fcc-343">**Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="f9fcc-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-344">**Count**</span></span>

- <span data-ttu-id="f9fcc-345">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="f9fcc-346">**Top-Schadsoftware-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="f9fcc-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-347">**Count**</span></span>

- <span data-ttu-id="f9fcc-348">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="f9fcc-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="f9fcc-349">**Top-Malware Empfänger (ATP)**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="f9fcc-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9fcc-350">**Count**</span></span>

<span data-ttu-id="f9fcc-351">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9fcc-352">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f9fcc-353">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="f9fcc-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f9fcc-354">Zum Anzeigen und Verwenden der Berichte müssen Sie Mitglied der angegebenen Rollengruppe im Security & Compliance Center **und** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="f9fcc-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="f9fcc-355">Im Security & Compliance Center müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="f9fcc-356">-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f9fcc-356">-Organization Management</span></span>

  <span data-ttu-id="f9fcc-357">-Sicherheits Administrator (Sie können dies auch im [Azure Active Directory Admin Center](https://aad.portal.azure.com) -Sicherheits Leser</span><span class="sxs-lookup"><span data-stu-id="f9fcc-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="f9fcc-358">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="f9fcc-359">In Exchange Online müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="f9fcc-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="f9fcc-360">-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f9fcc-360">-Organization Management</span></span>

  <span data-ttu-id="f9fcc-361">-Nur Ansichts Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f9fcc-361">-View-only Organization Management</span></span>

  <span data-ttu-id="f9fcc-362">-Nur anzeigende Empfänger</span><span class="sxs-lookup"><span data-stu-id="f9fcc-362">-View-Only Recipients</span></span>

  <span data-ttu-id="f9fcc-363">-Compliance-Management</span><span class="sxs-lookup"><span data-stu-id="f9fcc-363">-Compliance Management</span></span>

<span data-ttu-id="f9fcc-364">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="f9fcc-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9fcc-365">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f9fcc-365">Related topics</span></span>

[<span data-ttu-id="f9fcc-366">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f9fcc-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f9fcc-367">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f9fcc-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
