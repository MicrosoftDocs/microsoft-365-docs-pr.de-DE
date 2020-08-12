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
ms.openlocfilehash: acf74136fc61d38ea9aac47f36d96aa51a7b9905
ms.sourcegitcommit: 6319e73b3690b4cf1b7932f2b9f51c2c99e70eaa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46635034"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="cb84f-103">Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cb84f-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="cb84f-104">Zusätzlich zu den Nachrichtenfluss Berichten, die im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zur Verfügung stehen, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenübermittlungs Berichte zur Verfügung, mit denen Sie Ihre Microsoft 365-Organisation überwachen können.</span><span class="sxs-lookup"><span data-stu-id="cb84f-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="cb84f-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im [Security & Compliance Center](https://office.protection.com) anzeigen, indem Sie zum **Reports** \> **Dashboard**Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="cb84f-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cb84f-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="cb84f-108">Connector-Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-108">Connector report</span></span>

<span data-ttu-id="cb84f-109">Der **Bericht Connector** zeigt die Nachrichtenfluss Aktivität für die [eingehenden und ausgehenden Connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cb84f-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="cb84f-110">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **connectorbericht**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="cb84f-111">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connector-Berichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="cb84f-113">Berichtsansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-113">Report view for the Connector report</span></span>

<span data-ttu-id="cb84f-114">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cb84f-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="cb84f-115">**Anzeigen von Daten nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, die von organisiert werden:</span><span class="sxs-lookup"><span data-stu-id="cb84f-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="cb84f-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="cb84f-116">**Total**</span></span>
  - <span data-ttu-id="cb84f-117">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="cb84f-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="cb84f-118">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="cb84f-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="cb84f-119">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="cb84f-120">Um die Daten im Diagramm zu isolieren, verwenden Sie die Option **Daten für** SteuerelementAnzeigen, um eine dieser Optionen oder den **gesamten Nachrichtenfluss**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach dem Nachrichtenfluss im connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="cb84f-122">**Daten nach: TLS Usage**: in diesem Diagramm wird der prozentuale Anteil der TLS-Version (Transport Layer Security) für den Nachrichtenfluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="cb84f-123">Um die Daten im Diagramm zu isolieren, wählen Sie mithilfe des Steuerelements **Daten anzeigen für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="cb84f-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="cb84f-124">**Gesamter Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="cb84f-124">**All mail flow**</span></span>
  - <span data-ttu-id="cb84f-125">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="cb84f-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="cb84f-126">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="cb84f-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="cb84f-127">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-127">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="cb84f-129">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="cb84f-130">Detailtabellen Ansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-130">Details table view for the Connector report</span></span>

<span data-ttu-id="cb84f-131">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb84f-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cb84f-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="cb84f-132">**Date**</span></span>
- <span data-ttu-id="cb84f-133">**Verbindungsrichtung und-Name**</span><span class="sxs-lookup"><span data-stu-id="cb84f-133">**Connector direction and name**</span></span>
- <span data-ttu-id="cb84f-134">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="cb84f-134">**Connector type**</span></span>
- <span data-ttu-id="cb84f-135">**Forced TLS?**: der Wert **true** oder **false**.</span><span class="sxs-lookup"><span data-stu-id="cb84f-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="cb84f-136">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="cb84f-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="cb84f-137">**TLS 1,0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="cb84f-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="cb84f-138">**TLS 1,1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="cb84f-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="cb84f-139">**TLS 1,2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="cb84f-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="cb84f-140">**Volume**: die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cb84f-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="cb84f-141">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cb84f-142">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="cb84f-143">Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-143">Exchange transport rule report</span></span>

<span data-ttu-id="cb84f-144">Der **Exchange-Transportregel Bericht** zeigt die Auswirkungen von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) auf ein-und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="cb84f-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="cb84f-145">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Exchange-Transport Regel**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="cb84f-146">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="cb84f-148">Berichtsansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="cb84f-149">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cb84f-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="cb84f-150">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="cb84f-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Severity**: Dieses Diagramm zeigt die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem**Schweregrad sowie Nachrichten mit **niedrigem Schweregrad** .</span><span class="sxs-lookup"><span data-stu-id="cb84f-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="cb84f-152">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit schwere** Grad oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="cb84f-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="cb84f-153">Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="cb84f-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="cb84f-154">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von den DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="cb84f-155">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="cb84f-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="cb84f-156">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="cb84f-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="cb84f-157">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="cb84f-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="cb84f-158">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="cb84f-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="cb84f-159">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: in dieser Ansicht wird die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem Schweregrad**sowie Nachrichten mit **niedrigem Schweregrad** angezeigt, die von den DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="cb84f-160">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="cb84f-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="cb84f-161">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="cb84f-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="cb84f-162">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="cb84f-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="cb84f-163">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="cb84f-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="cb84f-164">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="cb84f-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="cb84f-165">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="cb84f-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb84f-166">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-166">Direction values</span></span>
- <span data-ttu-id="cb84f-167">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-167">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregel Bericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="cb84f-169">Detailtabellen Ansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="cb84f-170">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="cb84f-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb84f-171">**Anzeigen von Daten nach: Exchange-Transport Regeln**:</span><span class="sxs-lookup"><span data-stu-id="cb84f-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="cb84f-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="cb84f-172">**Date**</span></span>
  - <span data-ttu-id="cb84f-173">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="cb84f-173">**Transport rule**</span></span>
  - <span data-ttu-id="cb84f-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="cb84f-174">**Subject**</span></span>
  - <span data-ttu-id="cb84f-175">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="cb84f-175">**Sender address**</span></span>
  - <span data-ttu-id="cb84f-176">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="cb84f-176">**Recipient address**</span></span>
  - <span data-ttu-id="cb84f-177">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="cb84f-177">**Severity**</span></span>
  - <span data-ttu-id="cb84f-178">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="cb84f-178">**Direction**</span></span>

- <span data-ttu-id="cb84f-179">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="cb84f-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="cb84f-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="cb84f-180">**Date**</span></span>
  - <span data-ttu-id="cb84f-181">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="cb84f-181">**DLP policy**</span></span>
  - <span data-ttu-id="cb84f-182">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="cb84f-182">**Transport rule**</span></span>
  - <span data-ttu-id="cb84f-183">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="cb84f-183">**Subject**</span></span>
  - <span data-ttu-id="cb84f-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="cb84f-184">**Sender address**</span></span>
  - <span data-ttu-id="cb84f-185">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="cb84f-185">**Recipient address**</span></span>
  - <span data-ttu-id="cb84f-186">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="cb84f-186">**Severity**</span></span>
  - <span data-ttu-id="cb84f-187">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="cb84f-187">**Direction**</span></span>

<span data-ttu-id="cb84f-188">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="cb84f-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb84f-189">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="cb84f-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb84f-190">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-190">Direction values</span></span>
- <span data-ttu-id="cb84f-191">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-191">Severity values</span></span>

<span data-ttu-id="cb84f-192">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="cb84f-193">Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-193">Forwarding report</span></span>

<span data-ttu-id="cb84f-194">Der **Weiterleitungs Bericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="cb84f-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="cb84f-195">Weitergeleitete Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf ein kompromittiertes Konto hindeuten.</span><span class="sxs-lookup"><span data-stu-id="cb84f-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="cb84f-196">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **weiter Leitungs Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="cb84f-197">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleiten des Berichts-Widgets im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="cb84f-199">Berichtsansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="cb84f-200">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cb84f-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cb84f-201">**Daten anzeigen für: Weiterleitungs Methoden**: die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb84f-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="cb84f-202">**Transport Regel**: auch als [Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cb84f-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="cb84f-203">**Postfachregel**: auch [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)genannt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungs Methoden" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="cb84f-205">**Daten anzeigen für: Forwarding Domains**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleiten von Domänen" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="cb84f-207">**Daten anzeigen für: Forwarder**: die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb84f-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="cb84f-208">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="cb84f-208">**Transport rule**</span></span>
  - <span data-ttu-id="cb84f-209">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="cb84f-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarder-Ansicht im Weiterleitungs Bericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="cb84f-211">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="cb84f-212">Detailtabellen Ansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="cb84f-213">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb84f-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cb84f-214">**Weiterleitungen**: die Wert **Transport Regel** oder das Postfach, das die Posteingangsregel "Weiterleiten" enthält.</span><span class="sxs-lookup"><span data-stu-id="cb84f-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="cb84f-215">**Weiterleitungs**: der Wert für die **Postfachregel** oder die **Transport Regel**.</span><span class="sxs-lookup"><span data-stu-id="cb84f-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="cb84f-216">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="cb84f-216">**Recipient name**</span></span>
- <span data-ttu-id="cb84f-217">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="cb84f-217">**Recipient domain**</span></span>
- <span data-ttu-id="cb84f-218">**Details**: Dies ist der GUID-Wert der Nachrichtenfluss Regel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="cb84f-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="cb84f-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-219">**Count**</span></span>
- <span data-ttu-id="cb84f-220">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="cb84f-220">**First forward date**</span></span>

<span data-ttu-id="cb84f-221">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cb84f-222">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="cb84f-223">Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-223">Mailflow status report</span></span>

<span data-ttu-id="cb84f-224">Der **Nachrichtenfluss-Statusbericht** ähnelt dem [gesendeten und empfangenen e-Mail-Bericht](#sent-and-received-email-report), wobei zusätzliche Informationen zu e-Mail-Nachrichten zugelassen oder am Edge blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb84f-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="cb84f-225">Dies ist der einzige Bericht, der Informationen zum Edge-Schutz enthält, und zeigt, wie viele e-Mails blockiert werden, bevor Sie in den Dienst zur Evaluierung durch Exchange Online Protection (EoP) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="cb84f-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="cb84f-226">Es ist wichtig zu verstehen, dass wenn eine Nachricht an fünf Empfänger gesendet wird, wir Sie als fünf verschiedene Nachrichten und nicht eine Nachricht zählen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>  
<span data-ttu-id="cb84f-227">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Nachrichtenflussstatus Bericht**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="cb84f-228">Wenn Sie direkt zum **Nachrichtenflussstatus Bericht**wechseln möchten, öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenfluss-Statusbericht-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="cb84f-230">Typansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="cb84f-231">Wenn Sie den Bericht öffnen, ist die Registerkarte **Typ** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cb84f-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="cb84f-232">Diese Ansicht enthält standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="cb84f-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="cb84f-233">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="cb84f-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="cb84f-234">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="cb84f-234">**Direction**:</span></span>

  - <span data-ttu-id="cb84f-235">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="cb84f-235">**Inbound**</span></span>
  - <span data-ttu-id="cb84f-236">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="cb84f-236">**Outbound**</span></span>
  - <span data-ttu-id="cb84f-237">**Intra-org**: diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="cb84f-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="cb84f-238">Absender ABC@Domain.com wird an den Empfänger XYZ@Domain.com gesendet (separat **Inbound** von eingehend **und**ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="cb84f-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="cb84f-239">**Geben**Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cb84f-239">**Type**:</span></span>

  - <span data-ttu-id="cb84f-240">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="cb84f-240">**Good mail**</span></span>
  - <span data-ttu-id="cb84f-241">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="cb84f-241">**Malware**</span></span>
  - <span data-ttu-id="cb84f-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="cb84f-242">**Spam**</span></span>
  - <span data-ttu-id="cb84f-243">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="cb84f-243">**Edge protection**</span></span>
  - <span data-ttu-id="cb84f-244">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="cb84f-244">**Rule messages**</span></span>
  - <span data-ttu-id="cb84f-245">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="cb84f-245">**Phishing email**</span></span>

<span data-ttu-id="cb84f-246">Das Diagramm wird nach den **Typwerten** sortiert.</span><span class="sxs-lookup"><span data-stu-id="cb84f-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="cb84f-247">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="cb84f-247">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="cb84f-248">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="cb84f-248">The data table contains the following information:</span></span>

- <span data-ttu-id="cb84f-249">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="cb84f-249">**Direction**</span></span>
- <span data-ttu-id="cb84f-250">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cb84f-250">**Type**</span></span>
- <span data-ttu-id="cb84f-251">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="cb84f-251">**24 hours**</span></span>
- <span data-ttu-id="cb84f-252">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="cb84f-252">**3 days**</span></span>
- <span data-ttu-id="cb84f-253">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="cb84f-253">**7 days**</span></span>
- <span data-ttu-id="cb84f-254">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="cb84f-254">**15 days**</span></span>
- <span data-ttu-id="cb84f-255">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="cb84f-255">**30 days**</span></span>

<span data-ttu-id="cb84f-256">Wenn Sie auf **Kategorie auswählen klicken, um weitere Informationen zu**erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="cb84f-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="cb84f-257">**Phishing-e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="cb84f-258">**Schadsoftware in e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="cb84f-259">**Spamerkennungen**: Diese Auswahl führt Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="cb84f-260">**Spam blockierter Edge**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="cb84f-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="cb84f-261">**Export**:</span></span>

<span data-ttu-id="cb84f-262">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="cb84f-263">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="cb84f-264">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="cb84f-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="cb84f-265">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="cb84f-266">Typansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="cb84f-267">Richtungs Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="cb84f-268">Wenn Sie auf die Registerkarte **Richtung** klicken, werden die gleichen Standardfilter aus der **Typansicht verwendet** .</span><span class="sxs-lookup"><span data-stu-id="cb84f-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="cb84f-269">Das Diagramm ist nach **Richtungs** Werten angeordnet.</span><span class="sxs-lookup"><span data-stu-id="cb84f-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="cb84f-270">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="cb84f-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="cb84f-271">In der **Typansicht werden** dieselben Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb84f-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="cb84f-272">Die Datentabelle enthält dieselben Informationen aus der **Typen** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="cb84f-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="cb84f-273">Die **Kategorie Choose a category for More Details** available Selections and Behavior sind identisch mit der **Type** -Ansicht.</span><span class="sxs-lookup"><span data-stu-id="cb84f-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="cb84f-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="cb84f-274">**Export**:</span></span>

<span data-ttu-id="cb84f-275">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="cb84f-276">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="cb84f-277">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="cb84f-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="cb84f-278">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="cb84f-279">Richtungs Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="cb84f-280">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="cb84f-280">Sent and received email report</span></span>

<span data-ttu-id="cb84f-281">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="cb84f-281">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="cb84f-282">Der Unterschied zwischen diesem Bericht und dem Nachrichten [Fluss Statusbericht](#mailflow-status-report) lautet: dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edge-Schutz blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cb84f-282">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="cb84f-283">Die Aggregatansicht und die Detailansicht des Berichts erlauben eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="cb84f-283">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="cb84f-284">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **gesendete und empfangene e-Mails**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-284">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="cb84f-285">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-285">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendete und empfangene e-Mail-widget im Dashboard Berichte](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="cb84f-287">Berichtsansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-287">Report view for the Sent and received email report</span></span>

<span data-ttu-id="cb84f-288">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cb84f-288">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cb84f-289">**Aufschlüsseln nach: Typ**: das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="cb84f-289">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="cb84f-290">**Total**</span><span class="sxs-lookup"><span data-stu-id="cb84f-290">**Total**</span></span>
  - <span data-ttu-id="cb84f-291">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="cb84f-291">**Good mail**</span></span>
  - <span data-ttu-id="cb84f-292">**Schadsoftware (Anti-Malware)** (EoP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-292">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="cb84f-293">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="cb84f-293">**Spam detections**</span></span>
  - <span data-ttu-id="cb84f-294">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="cb84f-294">**Rule messages**</span></span>
  - <span data-ttu-id="cb84f-295">**Erweiterte Schadsoftware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-295">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="cb84f-296">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-296">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Geben Sie Ansicht im Bericht gesendete und empfangene e-Mails ein.](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="cb84f-298">**Aufschlüsseln nach: Direction**: das Diagramm zeigt **Gesamt**-, **eingehende**und **ausgehende** Daten.</span><span class="sxs-lookup"><span data-stu-id="cb84f-298">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="cb84f-299">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-299">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungs Ansicht im Bericht "gesendete und empfangene e-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="cb84f-301">**Drilldown nach** \> **Schadsoftware (Anti-Malware)**: mit dieser Auswahl gelangen Sie zur [Malware Erkennung in e-Mail-Bericht](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-301">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="cb84f-302">**Drilldown nach** \> **Spamerkennungen)**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cb84f-302">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="cb84f-303">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="cb84f-303">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb84f-304">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="cb84f-304">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb84f-305">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-305">Direction values</span></span>
- <span data-ttu-id="cb84f-306">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="cb84f-306">Type values</span></span>

<span data-ttu-id="cb84f-307">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-307">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="cb84f-308">Detailtabellen Ansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-308">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="cb84f-309">Wenn Sie auf **Tabelle Details anzeigen** in der Ansicht **aufschlüsseln nach: Richtung** oder **aufschlüsseln nach: Richtungs** Ansicht klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb84f-309">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="cb84f-310">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="cb84f-310">**Date (UTC)**</span></span>
- <span data-ttu-id="cb84f-311">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cb84f-311">**Type**</span></span>
- <span data-ttu-id="cb84f-312">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="cb84f-312">**Direction**</span></span>
- <span data-ttu-id="cb84f-313">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="cb84f-313">**Message count**</span></span>

<span data-ttu-id="cb84f-314">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="cb84f-314">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb84f-315">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="cb84f-315">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb84f-316">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="cb84f-316">Direction values</span></span>
- <span data-ttu-id="cb84f-317">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="cb84f-317">Type values</span></span>

<span data-ttu-id="cb84f-318">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-318">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="cb84f-319">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="cb84f-319">Top senders and recipients report</span></span>

<span data-ttu-id="cb84f-320">Der Bericht " **oberster Absender und Empfänger** " ist ein Kreisdiagramm, in dem Ihre oberen e-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cb84f-320">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="cb84f-321">Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **oberste Absender und Empfänger**aus.</span><span class="sxs-lookup"><span data-stu-id="cb84f-321">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="cb84f-322">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="cb84f-322">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Top-Absender und Empfänger-Widget im Dashboard Berichte](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="cb84f-324">Berichtsansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-324">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="cb84f-325">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cb84f-325">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cb84f-326">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="cb84f-326">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="cb84f-327">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-327">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="cb84f-328">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-328">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="cb84f-329">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-329">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="cb84f-330">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-330">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="cb84f-331">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="cb84f-331">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="cb84f-332">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb84f-332">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="cb84f-333">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-333">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "obere Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="cb84f-335">Detailtabellen Ansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="cb84f-335">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="cb84f-336">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="cb84f-336">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb84f-337">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="cb84f-337">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="cb84f-338">**Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="cb84f-338">**Top mail senders**</span></span>
  - <span data-ttu-id="cb84f-339">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-339">**Count**</span></span>

- <span data-ttu-id="cb84f-340">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-340">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="cb84f-341">**Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-341">**Top mail recipients**</span></span>
  - <span data-ttu-id="cb84f-342">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-342">**Count**</span></span>

- <span data-ttu-id="cb84f-343">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-343">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="cb84f-344">**Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-344">**Top spam recipients**</span></span>
  - <span data-ttu-id="cb84f-345">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-345">**Count**</span></span>

- <span data-ttu-id="cb84f-346">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-346">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="cb84f-347">**Top-Schadsoftware-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="cb84f-347">**Top malware recipients**</span></span>
  - <span data-ttu-id="cb84f-348">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-348">**Count**</span></span>

- <span data-ttu-id="cb84f-349">**Daten anzeigen für \> Top Malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cb84f-349">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="cb84f-350">**Top-Malware Empfänger (ATP)**</span><span class="sxs-lookup"><span data-stu-id="cb84f-350">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="cb84f-351">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb84f-351">**Count**</span></span>

<span data-ttu-id="cb84f-352">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="cb84f-352">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cb84f-353">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb84f-353">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="cb84f-354">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="cb84f-354">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="cb84f-355">Zum Anzeigen und Verwenden der Berichte müssen Sie Mitglied der angegebenen Rollengruppe im Security & Compliance Center **und** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="cb84f-355">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="cb84f-356">Im Security & Compliance Center müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="cb84f-356">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cb84f-357">-Organisationsverwaltung-Sicherheits Administrator (Dies können Sie auch im [Azure Active Directory Admin Center](https://aad.portal.azure.com) – Sicherheits Leser</span><span class="sxs-lookup"><span data-stu-id="cb84f-357">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="cb84f-358">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="cb84f-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="cb84f-359">In Exchange Online müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="cb84f-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cb84f-360">-Organisationsverwaltung-nur Ansichts Organisationsverwaltung-nur Empfänger – Compliance-Management</span><span class="sxs-lookup"><span data-stu-id="cb84f-360">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="cb84f-361">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="cb84f-361">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb84f-362">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cb84f-362">Related topics</span></span>

[<span data-ttu-id="cb84f-363">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cb84f-363">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cb84f-364">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cb84f-364">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="cb84f-365">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cb84f-365">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="cb84f-366">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cb84f-366">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
