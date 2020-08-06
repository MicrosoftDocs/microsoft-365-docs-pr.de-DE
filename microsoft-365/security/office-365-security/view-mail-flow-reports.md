---
title: Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte"
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
description: Administratoren können Informationen zu den Nachrichtenfluss Berichten erhalten, die im Dashboard Berichte im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578018"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="a400b-103">Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a400b-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="a400b-104">Zusätzlich zu den Nachrichtenfluss Berichten, die im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zur Verfügung stehen, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenübermittlungs Berichte zur Verfügung, mit denen Sie Ihre Microsoft 365-Organisation überwachen können.</span><span class="sxs-lookup"><span data-stu-id="a400b-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="a400b-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im [Security & Compliance Center](https://office.protection.com) anzeigen, indem Sie zum **Reports** \> **Dashboard**Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="a400b-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a400b-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="a400b-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="a400b-108">Connector-Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-108">Connector report</span></span>

<span data-ttu-id="a400b-109">Der **Bericht Connector** zeigt die Nachrichtenfluss Aktivität für die [eingehenden und ausgehenden Connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a400b-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="a400b-110">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **connectorbericht**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="a400b-111">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="a400b-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connector-Berichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="a400b-113">Berichtsansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-113">Report view for the Connector report</span></span>

<span data-ttu-id="a400b-114">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a400b-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="a400b-115">**Anzeigen von Daten nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, die von organisiert werden:</span><span class="sxs-lookup"><span data-stu-id="a400b-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="a400b-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="a400b-116">**Total**</span></span>
  - <span data-ttu-id="a400b-117">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="a400b-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a400b-118">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="a400b-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a400b-119">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="a400b-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="a400b-120">Um die Daten im Diagramm zu isolieren, verwenden Sie die Option **Daten für** SteuerelementAnzeigen, um eine dieser Optionen oder den **gesamten Nachrichtenfluss**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a400b-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach dem Nachrichtenfluss im connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="a400b-122">**Daten nach: TLS Usage**: in diesem Diagramm wird der prozentuale Anteil der TLS-Version (Transport Layer Security) für den Nachrichtenfluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a400b-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="a400b-123">Um die Daten im Diagramm zu isolieren, wählen Sie mithilfe des Steuerelements **Daten anzeigen für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a400b-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="a400b-124">**Gesamter Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="a400b-124">**All mail flow**</span></span>
  - <span data-ttu-id="a400b-125">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="a400b-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a400b-126">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="a400b-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a400b-127">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="a400b-127">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="a400b-129">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="a400b-130">Detailtabellen Ansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-130">Details table view for the Connector report</span></span>

<span data-ttu-id="a400b-131">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a400b-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a400b-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="a400b-132">**Date**</span></span>
- <span data-ttu-id="a400b-133">**Verbindungsrichtung und-Name**</span><span class="sxs-lookup"><span data-stu-id="a400b-133">**Connector direction and name**</span></span>
- <span data-ttu-id="a400b-134">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="a400b-134">**Connector type**</span></span>
- <span data-ttu-id="a400b-135">**Forced TLS?**: der Wert **true** oder **false**.</span><span class="sxs-lookup"><span data-stu-id="a400b-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="a400b-136">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="a400b-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="a400b-137">**TLS 1,0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="a400b-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="a400b-138">**TLS 1,1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="a400b-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="a400b-139">**TLS 1,2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="a400b-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="a400b-140">**Volume**: die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a400b-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="a400b-141">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a400b-142">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="a400b-143">Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-143">Exchange transport rule report</span></span>

<span data-ttu-id="a400b-144">Der **Exchange-Transportregel Bericht** zeigt die Auswirkungen von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) auf ein-und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a400b-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="a400b-145">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Exchange-Transport Regel**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="a400b-146">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="a400b-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a400b-148">Berichtsansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="a400b-149">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a400b-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="a400b-150">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="a400b-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="a400b-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Severity**: Dieses Diagramm zeigt die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem**Schweregrad sowie Nachrichten mit **niedrigem Schweregrad** .</span><span class="sxs-lookup"><span data-stu-id="a400b-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="a400b-152">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit schwere** Grad oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="a400b-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="a400b-153">Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="a400b-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="a400b-154">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von den DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="a400b-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="a400b-155">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="a400b-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a400b-156">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="a400b-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a400b-157">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="a400b-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a400b-158">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="a400b-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="a400b-159">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: in dieser Ansicht wird die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem Schweregrad**sowie Nachrichten mit **niedrigem Schweregrad** angezeigt, die von den DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="a400b-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="a400b-160">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="a400b-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a400b-161">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="a400b-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a400b-162">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="a400b-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a400b-163">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="a400b-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="a400b-164">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="a400b-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="a400b-165">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="a400b-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="a400b-166">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="a400b-166">Direction values</span></span>
- <span data-ttu-id="a400b-167">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="a400b-167">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregel Bericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a400b-169">Detailtabellen Ansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="a400b-170">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="a400b-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a400b-171">**Anzeigen von Daten nach: Exchange-Transport Regeln**:</span><span class="sxs-lookup"><span data-stu-id="a400b-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="a400b-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="a400b-172">**Date**</span></span>
  - <span data-ttu-id="a400b-173">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="a400b-173">**Transport rule**</span></span>
  - <span data-ttu-id="a400b-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="a400b-174">**Subject**</span></span>
  - <span data-ttu-id="a400b-175">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="a400b-175">**Sender address**</span></span>
  - <span data-ttu-id="a400b-176">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="a400b-176">**Recipient address**</span></span>
  - <span data-ttu-id="a400b-177">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="a400b-177">**Severity**</span></span>
  - <span data-ttu-id="a400b-178">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="a400b-178">**Direction**</span></span>

- <span data-ttu-id="a400b-179">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="a400b-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="a400b-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="a400b-180">**Date**</span></span>
  - <span data-ttu-id="a400b-181">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="a400b-181">**DLP policy**</span></span>
  - <span data-ttu-id="a400b-182">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="a400b-182">**Transport rule**</span></span>
  - <span data-ttu-id="a400b-183">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="a400b-183">**Subject**</span></span>
  - <span data-ttu-id="a400b-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="a400b-184">**Sender address**</span></span>
  - <span data-ttu-id="a400b-185">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="a400b-185">**Recipient address**</span></span>
  - <span data-ttu-id="a400b-186">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="a400b-186">**Severity**</span></span>
  - <span data-ttu-id="a400b-187">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="a400b-187">**Direction**</span></span>

<span data-ttu-id="a400b-188">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="a400b-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a400b-189">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="a400b-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="a400b-190">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="a400b-190">Direction values</span></span>
- <span data-ttu-id="a400b-191">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="a400b-191">Severity values</span></span>

<span data-ttu-id="a400b-192">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="a400b-193">Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-193">Forwarding report</span></span>

<span data-ttu-id="a400b-194">Der **Weiterleitungs Bericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="a400b-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="a400b-195">Weitergeleitete Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf ein kompromittiertes Konto hindeuten.</span><span class="sxs-lookup"><span data-stu-id="a400b-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="a400b-196">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **weiter Leitungs Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="a400b-197">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="a400b-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleiten des Berichts-Widgets im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="a400b-199">Berichtsansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="a400b-200">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a400b-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a400b-201">**Daten anzeigen für: Weiterleitungs Methoden**: die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a400b-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="a400b-202">**Transport Regel**: auch als [Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a400b-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="a400b-203">**Postfachregel**: auch [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)genannt.</span><span class="sxs-lookup"><span data-stu-id="a400b-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungs Methoden" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="a400b-205">**Daten anzeigen für: Forwarding Domains**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung darstellen.</span><span class="sxs-lookup"><span data-stu-id="a400b-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleiten von Domänen" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="a400b-207">**Daten anzeigen für: Forwarder**: die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a400b-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="a400b-208">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="a400b-208">**Transport rule**</span></span>
  - <span data-ttu-id="a400b-209">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="a400b-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarder-Ansicht im Weiterleitungs Bericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="a400b-211">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="a400b-212">Detailtabellen Ansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="a400b-213">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a400b-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a400b-214">**Weiterleitungen**: die Wert **Transport Regel** oder das Postfach, das die Posteingangsregel "Weiterleiten" enthält.</span><span class="sxs-lookup"><span data-stu-id="a400b-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="a400b-215">**Weiterleitungs**: der Wert für die **Postfachregel** oder die **Transport Regel**.</span><span class="sxs-lookup"><span data-stu-id="a400b-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="a400b-216">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="a400b-216">**Recipient name**</span></span>
- <span data-ttu-id="a400b-217">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="a400b-217">**Recipient domain**</span></span>
- <span data-ttu-id="a400b-218">**Details**: Dies ist der GUID-Wert der Nachrichtenfluss Regel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="a400b-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="a400b-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-219">**Count**</span></span>
- <span data-ttu-id="a400b-220">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="a400b-220">**First forward date**</span></span>

<span data-ttu-id="a400b-221">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a400b-222">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="a400b-223">Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-223">Mailflow status report</span></span>

<span data-ttu-id="a400b-224">Der **Nachrichtenfluss-Statusbericht** ähnelt dem [gesendeten und empfangenen e-Mail-Bericht](#sent-and-received-email-report), wobei zusätzliche Informationen zu e-Mail-Nachrichten zugelassen oder am Edge blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a400b-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="a400b-225">Dies ist der einzige Bericht, der Informationen zum Edge-Schutz enthält, und zeigt, wie viele e-Mails blockiert werden, bevor Sie in den Dienst zur Evaluierung durch Exchange Online Protection (EoP) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="a400b-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="a400b-226">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Nachrichtenflussstatus Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="a400b-227">Wenn Sie direkt zum **Nachrichtenflussstatus Bericht**wechseln möchten, öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="a400b-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenfluss-Statusbericht-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="a400b-229">Typansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="a400b-230">Wenn Sie den Bericht öffnen, ist die Registerkarte **Typ** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a400b-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="a400b-231">Diese Ansicht enthält standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="a400b-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a400b-232">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="a400b-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="a400b-233">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="a400b-233">**Direction**:</span></span>

  - <span data-ttu-id="a400b-234">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="a400b-234">**Inbound**</span></span>
  - <span data-ttu-id="a400b-235">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="a400b-235">**Outbound**</span></span>
  - <span data-ttu-id="a400b-236">**Intra-org** (wird getrennt von einem **eingehenden** und **ausgehenden**gezählt)</span><span class="sxs-lookup"><span data-stu-id="a400b-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="a400b-237">**Geben**Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a400b-237">**Type**:</span></span>

  - <span data-ttu-id="a400b-238">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="a400b-238">**Good mail**</span></span>
  - <span data-ttu-id="a400b-239">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="a400b-239">**Malware**</span></span>
  - <span data-ttu-id="a400b-240">**Spam**</span><span class="sxs-lookup"><span data-stu-id="a400b-240">**Spam**</span></span>
  - <span data-ttu-id="a400b-241">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="a400b-241">**Edge protection**</span></span>
  - <span data-ttu-id="a400b-242">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="a400b-242">**Rule messages**</span></span>
  - <span data-ttu-id="a400b-243">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="a400b-243">**Phishing email**</span></span>

<span data-ttu-id="a400b-244">Das Diagramm wird nach den **Typwerten** sortiert.</span><span class="sxs-lookup"><span data-stu-id="a400b-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="a400b-245">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="a400b-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="a400b-246">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="a400b-246">The data table contains the following information:</span></span>

- <span data-ttu-id="a400b-247">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="a400b-247">**Direction**</span></span>
- <span data-ttu-id="a400b-248">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a400b-248">**Type**</span></span>
- <span data-ttu-id="a400b-249">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="a400b-249">**24 hours**</span></span>
- <span data-ttu-id="a400b-250">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="a400b-250">**3 days**</span></span>
- <span data-ttu-id="a400b-251">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="a400b-251">**7 days**</span></span>
- <span data-ttu-id="a400b-252">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="a400b-252">**15 days**</span></span>
- <span data-ttu-id="a400b-253">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="a400b-253">**30 days**</span></span>

<span data-ttu-id="a400b-254">Wenn Sie auf **Kategorie auswählen klicken, um weitere Informationen zu**erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="a400b-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="a400b-255">**Phishing-e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a400b-256">**Schadsoftware in e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a400b-257">**Spamerkennungen**: Diese Auswahl führt Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="a400b-258">**Spam blockierter Edge**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a400b-259">**Export**:</span><span class="sxs-lookup"><span data-stu-id="a400b-259">**Export**:</span></span>

<span data-ttu-id="a400b-260">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="a400b-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a400b-261">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="a400b-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a400b-262">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="a400b-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a400b-263">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="a400b-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="a400b-264">Typansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="a400b-265">Richtungs Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="a400b-266">Wenn Sie auf die Registerkarte **Richtung** klicken, werden die gleichen Standardfilter aus der **Typansicht verwendet** .</span><span class="sxs-lookup"><span data-stu-id="a400b-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="a400b-267">Das Diagramm ist nach **Richtungs** Werten angeordnet.</span><span class="sxs-lookup"><span data-stu-id="a400b-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="a400b-268">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="a400b-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="a400b-269">In der **Typansicht werden** dieselben Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a400b-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="a400b-270">Die Datentabelle enthält dieselben Informationen aus der **Typen** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="a400b-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="a400b-271">Die **Kategorie Choose a category for More Details** available Selections and Behavior sind identisch mit der **Type** -Ansicht.</span><span class="sxs-lookup"><span data-stu-id="a400b-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="a400b-272">**Export**:</span><span class="sxs-lookup"><span data-stu-id="a400b-272">**Export**:</span></span>

<span data-ttu-id="a400b-273">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="a400b-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a400b-274">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="a400b-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a400b-275">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="a400b-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a400b-276">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="a400b-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="a400b-277">Richtungs Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="a400b-278">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="a400b-278">Sent and received email report</span></span>

<span data-ttu-id="a400b-279">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="a400b-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="a400b-280">Der Unterschied zwischen diesem Bericht und dem Nachrichten [Fluss Statusbericht](#mailflow-status-report) lautet: dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edge-Schutz blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a400b-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="a400b-281">Die Aggregatansicht und die Detailansicht des Berichts erlauben eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="a400b-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="a400b-282">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **gesendete und empfangene e-Mails**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="a400b-283">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="a400b-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendete und empfangene e-Mail-widget im Dashboard Berichte](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a400b-285">Berichtsansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="a400b-286">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a400b-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a400b-287">**Aufschlüsseln nach: Typ**: das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="a400b-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="a400b-288">**Total**</span><span class="sxs-lookup"><span data-stu-id="a400b-288">**Total**</span></span>
  - <span data-ttu-id="a400b-289">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="a400b-289">**Good mail**</span></span>
  - <span data-ttu-id="a400b-290">**Schadsoftware (Anti-Malware)** (EoP)</span><span class="sxs-lookup"><span data-stu-id="a400b-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="a400b-291">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="a400b-291">**Spam detections**</span></span>
  - <span data-ttu-id="a400b-292">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="a400b-292">**Rule messages**</span></span>
  - <span data-ttu-id="a400b-293">**Erweiterte Schadsoftware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="a400b-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="a400b-294">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a400b-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Geben Sie Ansicht im Bericht gesendete und empfangene e-Mails ein.](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="a400b-296">**Aufschlüsseln nach: Direction**: das Diagramm zeigt **Gesamt**-, **eingehende**und **ausgehende** Daten.</span><span class="sxs-lookup"><span data-stu-id="a400b-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="a400b-297">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a400b-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungs Ansicht im Bericht "gesendete und empfangene e-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="a400b-299">**Drilldown nach** \> **Schadsoftware (Anti-Malware)**: mit dieser Auswahl gelangen Sie zur [Malware Erkennung in e-Mail-Bericht](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="a400b-300">**Drilldown nach** \> **Spamerkennungen)**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a400b-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a400b-301">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="a400b-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a400b-302">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="a400b-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="a400b-303">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="a400b-303">Direction values</span></span>
- <span data-ttu-id="a400b-304">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="a400b-304">Type values</span></span>

<span data-ttu-id="a400b-305">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a400b-306">Detailtabellen Ansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="a400b-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="a400b-307">Wenn Sie auf **Tabelle Details anzeigen** in der Ansicht **aufschlüsseln nach: Richtung** oder **aufschlüsseln nach: Richtungs** Ansicht klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a400b-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="a400b-308">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="a400b-308">**Date (UTC)**</span></span>
- <span data-ttu-id="a400b-309">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a400b-309">**Type**</span></span>
- <span data-ttu-id="a400b-310">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="a400b-310">**Direction**</span></span>
- <span data-ttu-id="a400b-311">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="a400b-311">**Message count**</span></span>

<span data-ttu-id="a400b-312">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="a400b-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a400b-313">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="a400b-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="a400b-314">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="a400b-314">Direction values</span></span>
- <span data-ttu-id="a400b-315">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="a400b-315">Type values</span></span>

<span data-ttu-id="a400b-316">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="a400b-317">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="a400b-317">Top senders and recipients report</span></span>

<span data-ttu-id="a400b-318">Der Bericht " **oberster Absender und Empfänger** " ist ein Kreisdiagramm, in dem Ihre oberen e-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a400b-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="a400b-319">Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **oberste Absender und Empfänger**aus.</span><span class="sxs-lookup"><span data-stu-id="a400b-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="a400b-320">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="a400b-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Top-Absender und Empfänger-Widget im Dashboard Berichte](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a400b-322">Berichtsansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="a400b-323">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a400b-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a400b-324">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="a400b-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="a400b-325">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="a400b-326">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="a400b-327">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="a400b-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="a400b-328">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="a400b-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="a400b-329">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="a400b-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="a400b-330">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a400b-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="a400b-331">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "obere Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a400b-333">Detailtabellen Ansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="a400b-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="a400b-334">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="a400b-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a400b-335">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="a400b-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="a400b-336">**Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="a400b-336">**Top mail senders**</span></span>
  - <span data-ttu-id="a400b-337">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-337">**Count**</span></span>

- <span data-ttu-id="a400b-338">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="a400b-339">**Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="a400b-340">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-340">**Count**</span></span>

- <span data-ttu-id="a400b-341">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="a400b-342">**Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="a400b-343">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-343">**Count**</span></span>

- <span data-ttu-id="a400b-344">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="a400b-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="a400b-345">**Top-Schadsoftware-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a400b-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="a400b-346">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-346">**Count**</span></span>

- <span data-ttu-id="a400b-347">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="a400b-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="a400b-348">**Top-Malware Empfänger (ATP)**</span><span class="sxs-lookup"><span data-stu-id="a400b-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="a400b-349">**Count**</span><span class="sxs-lookup"><span data-stu-id="a400b-349">**Count**</span></span>

<span data-ttu-id="a400b-350">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="a400b-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a400b-351">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a400b-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="a400b-352">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="a400b-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="a400b-353">Zum Anzeigen und Verwenden der Berichte müssen Sie Mitglied der angegebenen Rollengruppe im Security & Compliance Center **und** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="a400b-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="a400b-354">Im Security & Compliance Center müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="a400b-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="a400b-355">-Organisationsverwaltung-Sicherheits Administrator (Dies können Sie auch im [Azure Active Directory Admin Center](https://aad.portal.azure.com) – Sicherheits Leser</span><span class="sxs-lookup"><span data-stu-id="a400b-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="a400b-356">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a400b-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="a400b-357">In Exchange Online müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="a400b-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="a400b-358">-Organisationsverwaltung-nur Ansichts Organisationsverwaltung-nur Empfänger – Compliance-Management</span><span class="sxs-lookup"><span data-stu-id="a400b-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="a400b-359">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="a400b-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a400b-360">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a400b-360">Related topics</span></span>

[<span data-ttu-id="a400b-361">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a400b-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a400b-362">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a400b-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="a400b-363">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a400b-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="a400b-364">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a400b-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
