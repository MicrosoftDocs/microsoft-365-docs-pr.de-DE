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
ms.openlocfilehash: 1ededf2d0d693c537c159c52d00deb03f278b4b2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659465"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="b166d-103">Anzeigen von Nachrichtenfluss Berichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b166d-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b166d-104">Zusätzlich zu den Nachrichtenfluss Berichten, die im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zur Verfügung stehen, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenübermittlungs Berichte zur Verfügung, mit denen Sie Ihre Microsoft 365-Organisation überwachen können.</span><span class="sxs-lookup"><span data-stu-id="b166d-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="b166d-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im [Security & Compliance Center](https://office.protection.com) anzeigen, indem Sie zum  \> **Dashboard** Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="b166d-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b166d-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="b166d-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="b166d-108">Connector-Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-108">Connector report</span></span>

<span data-ttu-id="b166d-109">Der **Bericht Connector** zeigt die Nachrichtenfluss Aktivität für die [eingehenden und ausgehenden Connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b166d-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="b166d-110">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie  zum \> **Dashboard** Berichte, und wählen Sie **connectorbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="b166d-111">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="b166d-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connector-Berichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="b166d-113">Berichtsansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-113">Report view for the Connector report</span></span>

<span data-ttu-id="b166d-114">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b166d-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="b166d-115">**Anzeigen von Daten nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, die von organisiert werden:</span><span class="sxs-lookup"><span data-stu-id="b166d-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="b166d-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="b166d-116">**Total**</span></span>
  - <span data-ttu-id="b166d-117">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="b166d-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b166d-118">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="b166d-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b166d-119">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="b166d-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="b166d-120">Um die Daten im Diagramm zu isolieren, verwenden Sie die Option **Daten für** SteuerelementAnzeigen, um eine dieser Optionen oder den **gesamten Nachrichtenfluss** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b166d-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach dem Nachrichtenfluss im connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="b166d-122">**Daten nach: TLS Usage**: in diesem Diagramm wird der prozentuale Anteil der TLS-Version (Transport Layer Security) für den Nachrichtenfluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="b166d-123">Um die Daten im Diagramm zu isolieren, wählen Sie mithilfe des Steuerelements **Daten anzeigen für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b166d-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="b166d-124">**Gesamter Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="b166d-124">**All mail flow**</span></span>
  - <span data-ttu-id="b166d-125">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="b166d-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b166d-126">**An das Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="b166d-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b166d-127">Einen bestimmten Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="b166d-127">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="b166d-129">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="b166d-130">Detailtabellen Ansicht für den connectorbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-130">Details table view for the Connector report</span></span>

<span data-ttu-id="b166d-131">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b166d-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b166d-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="b166d-132">**Date**</span></span>
- <span data-ttu-id="b166d-133">**Verbindungsrichtung und-Name**</span><span class="sxs-lookup"><span data-stu-id="b166d-133">**Connector direction and name**</span></span>
- <span data-ttu-id="b166d-134">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="b166d-134">**Connector type**</span></span>
- <span data-ttu-id="b166d-135">**Forced TLS?**: der Wert **true** oder **false**.</span><span class="sxs-lookup"><span data-stu-id="b166d-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="b166d-136">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="b166d-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="b166d-137">**TLS 1,0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="b166d-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="b166d-138">**TLS 1,1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="b166d-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="b166d-139">**TLS 1,2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="b166d-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="b166d-140">**Volume**: die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b166d-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="b166d-141">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b166d-142">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b166d-143">Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-143">Exchange transport rule report</span></span>

<span data-ttu-id="b166d-144">Der **Exchange-Transportregel Bericht** zeigt die Auswirkungen von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) auf ein-und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b166d-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b166d-145">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie  zum \> **Dashboard** Berichte, und wählen Sie **Exchange-Transport Regel** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="b166d-146">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="b166d-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b166d-148">Berichtsansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="b166d-149">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b166d-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="b166d-150">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="b166d-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="b166d-151">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufschlüsseln nach: Severity**: Dieses Diagramm zeigt die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem** Schweregrad sowie Nachrichten mit **niedrigem Schweregrad** .</span><span class="sxs-lookup"><span data-stu-id="b166d-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b166d-152">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit schwere** Grad oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="b166d-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b166d-153">Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="b166d-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b166d-154">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von den DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="b166d-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="b166d-155">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="b166d-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b166d-156">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="b166d-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b166d-157">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b166d-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b166d-158">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="b166d-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="b166d-159">**Daten anzeigen nach: DLP Exchange-Transportregeln** \> **Aufschlüsseln nach: Direction**: in dieser Ansicht wird die Anzahl der Nachrichten mit **hohem schwere** Grad und **mittlerem Schweregrad** sowie Nachrichten mit **niedrigem Schweregrad** angezeigt, die von den DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="b166d-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="b166d-160">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="b166d-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b166d-161">**Daten anzeigen für: alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="b166d-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b166d-162">**Daten anzeigen für: kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b166d-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b166d-163">**Daten anzeigen für: geringes Inhaltsvolumen erkannter US-Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="b166d-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="b166d-164">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="b166d-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="b166d-165">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b166d-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="b166d-166">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="b166d-166">Direction values</span></span>
- <span data-ttu-id="b166d-167">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="b166d-167">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregel Bericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b166d-169">Detailtabellen Ansicht für den Exchange-Transportregel Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="b166d-170">Wenn Sie auf **Detailtabelle anzeigen** klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="b166d-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b166d-171">**Anzeigen von Daten nach: Exchange-Transport Regeln**:</span><span class="sxs-lookup"><span data-stu-id="b166d-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="b166d-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="b166d-172">**Date**</span></span>
  - <span data-ttu-id="b166d-173">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="b166d-173">**Transport rule**</span></span>
  - <span data-ttu-id="b166d-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="b166d-174">**Subject**</span></span>
  - <span data-ttu-id="b166d-175">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="b166d-175">**Sender address**</span></span>
  - <span data-ttu-id="b166d-176">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="b166d-176">**Recipient address**</span></span>
  - <span data-ttu-id="b166d-177">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="b166d-177">**Severity**</span></span>
  - <span data-ttu-id="b166d-178">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="b166d-178">**Direction**</span></span>

- <span data-ttu-id="b166d-179">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="b166d-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="b166d-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="b166d-180">**Date**</span></span>
  - <span data-ttu-id="b166d-181">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="b166d-181">**DLP policy**</span></span>
  - <span data-ttu-id="b166d-182">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="b166d-182">**Transport rule**</span></span>
  - <span data-ttu-id="b166d-183">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="b166d-183">**Subject**</span></span>
  - <span data-ttu-id="b166d-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="b166d-184">**Sender address**</span></span>
  - <span data-ttu-id="b166d-185">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="b166d-185">**Recipient address**</span></span>
  - <span data-ttu-id="b166d-186">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="b166d-186">**Severity**</span></span>
  - <span data-ttu-id="b166d-187">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="b166d-187">**Direction**</span></span>

<span data-ttu-id="b166d-188">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="b166d-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b166d-189">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b166d-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="b166d-190">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="b166d-190">Direction values</span></span>
- <span data-ttu-id="b166d-191">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="b166d-191">Severity values</span></span>

<span data-ttu-id="b166d-192">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b166d-193">Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-193">Forwarding report</span></span>

<span data-ttu-id="b166d-194">Der **Weiterleitungs Bericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="b166d-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="b166d-195">Weitergeleitete Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf ein kompromittiertes Konto hindeuten.</span><span class="sxs-lookup"><span data-stu-id="b166d-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="b166d-196">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie  zum \> **Dashboard** Berichte, und wählen Sie **weiter Leitungs Bericht** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="b166d-197">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="b166d-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleiten des Berichts-Widgets im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="b166d-199">Berichtsansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="b166d-200">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b166d-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b166d-201">**Daten anzeigen für: Weiterleitungs Methoden**: die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b166d-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="b166d-202">**Transport Regel**: auch als [Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b166d-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="b166d-203">**Postfachregel**: auch [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)genannt.</span><span class="sxs-lookup"><span data-stu-id="b166d-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungs Methoden" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="b166d-205">**Daten anzeigen für: Forwarding Domains**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung darstellen.</span><span class="sxs-lookup"><span data-stu-id="b166d-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleiten von Domänen" im Weiterleitungs Bericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="b166d-207">**Daten anzeigen für: Forwarder**: die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b166d-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="b166d-208">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="b166d-208">**Transport rule**</span></span>
  - <span data-ttu-id="b166d-209">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="b166d-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarder-Ansicht im Weiterleitungs Bericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="b166d-211">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="b166d-212">Detailtabellen Ansicht für den Weiterleitungs Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="b166d-213">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b166d-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b166d-214">**Weiterleitungen**: die Wert **Transport Regel** oder das Postfach, das die Posteingangsregel "Weiterleiten" enthält.</span><span class="sxs-lookup"><span data-stu-id="b166d-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="b166d-215">**Weiterleitungs**: der Wert für die **Postfachregel** oder die **Transport Regel**.</span><span class="sxs-lookup"><span data-stu-id="b166d-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="b166d-216">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="b166d-216">**Recipient name**</span></span>
- <span data-ttu-id="b166d-217">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="b166d-217">**Recipient domain**</span></span>
- <span data-ttu-id="b166d-218">**Details**: Dies ist der GUID-Wert der Nachrichtenfluss Regel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="b166d-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="b166d-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-219">**Count**</span></span>
- <span data-ttu-id="b166d-220">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="b166d-220">**First forward date**</span></span>

<span data-ttu-id="b166d-221">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b166d-222">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b166d-223">Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-223">Mailflow status report</span></span>

<span data-ttu-id="b166d-224">Der **Nachrichtenfluss-Statusbericht** ähnelt dem [gesendeten und empfangenen e-Mail-Bericht](#sent-and-received-email-report), wobei zusätzliche Informationen zu e-Mail-Nachrichten zugelassen oder am Edge blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="b166d-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b166d-225">Dies ist der einzige Bericht, der Informationen zum Edge-Schutz enthält, und zeigt, wie viele e-Mails blockiert werden, bevor Sie in den Dienst zur Evaluierung durch Exchange Online Protection (EoP) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b166d-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b166d-226">Es ist wichtig zu verstehen, dass wenn eine Nachricht an fünf Empfänger gesendet wird, wir Sie als fünf verschiedene Nachrichten und nicht eine Nachricht zählen.</span><span class="sxs-lookup"><span data-stu-id="b166d-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="b166d-227">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie  zum \> **Dashboard** Berichte, und wählen Sie **Nachrichtenflussstatus Bericht** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="b166d-228">Wenn Sie direkt zum **Nachrichtenflussstatus Bericht** wechseln möchten, öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="b166d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenfluss-Statusbericht-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b166d-230">Typansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b166d-231">Wenn Sie den Bericht öffnen, ist die Registerkarte **Typ** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b166d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b166d-232">Diese Ansicht enthält standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="b166d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b166d-233">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="b166d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="b166d-234">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="b166d-234">**Direction**:</span></span>

  - <span data-ttu-id="b166d-235">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-235">**Inbound**</span></span>
  - <span data-ttu-id="b166d-236">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-236">**Outbound**</span></span>
  - <span data-ttu-id="b166d-237">**Intra-org**: diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="b166d-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b166d-238">Absender ABC@Domain.com wird an den Empfänger XYZ@Domain.com gesendet (separat  von eingehend **und** ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="b166d-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="b166d-239">**Geben** Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b166d-239">**Type**:</span></span>

  - <span data-ttu-id="b166d-240">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="b166d-240">**Good mail**</span></span>
  - <span data-ttu-id="b166d-241">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="b166d-241">**Malware**</span></span>
  - <span data-ttu-id="b166d-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="b166d-242">**Spam**</span></span>
  - <span data-ttu-id="b166d-243">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="b166d-243">**Edge protection**</span></span>
  - <span data-ttu-id="b166d-244">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b166d-244">**Rule messages**</span></span>
  - <span data-ttu-id="b166d-245">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="b166d-245">**Phishing email**</span></span>

<span data-ttu-id="b166d-246">Das Diagramm wird nach den **Typwerten** sortiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b166d-247">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="b166d-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b166d-248">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="b166d-248">The data table contains the following information:</span></span>

- <span data-ttu-id="b166d-249">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="b166d-249">**Direction**</span></span>
- <span data-ttu-id="b166d-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="b166d-250">**Type**</span></span>
- <span data-ttu-id="b166d-251">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="b166d-251">**24 hours**</span></span>
- <span data-ttu-id="b166d-252">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="b166d-252">**3 days**</span></span>
- <span data-ttu-id="b166d-253">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="b166d-253">**7 days**</span></span>
- <span data-ttu-id="b166d-254">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="b166d-254">**15 days**</span></span>
- <span data-ttu-id="b166d-255">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="b166d-255">**30 days**</span></span>

<span data-ttu-id="b166d-256">Wenn Sie auf **Kategorie auswählen klicken, um weitere Informationen zu** erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="b166d-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b166d-257">**Phishing-e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b166d-258">**Schadsoftware in e-Mails**: mit dieser Auswahl gelangen Sie zum [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b166d-259">**Spamerkennungen**: Diese Auswahl führt Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b166d-260">**Spam blockierter Edge**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b166d-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="b166d-261">**Export**:</span></span>

<span data-ttu-id="b166d-262">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="b166d-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b166d-263">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="b166d-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b166d-264">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b166d-265">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="b166d-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b166d-266">Typansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b166d-267">Richtungs Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b166d-268">Wenn Sie auf die Registerkarte **Richtung** klicken, werden die gleichen Standardfilter aus der **Typansicht verwendet** .</span><span class="sxs-lookup"><span data-stu-id="b166d-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b166d-269">Das Diagramm ist nach **Richtungs** Werten angeordnet.</span><span class="sxs-lookup"><span data-stu-id="b166d-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b166d-270">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="b166d-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="b166d-271">In der **Typansicht werden** dieselben Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="b166d-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b166d-272">Die Datentabelle enthält dieselben Informationen aus der **Typen** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="b166d-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b166d-273">Die **Kategorie Choose a category for More Details** available Selections and Behavior sind identisch mit der **Type** -Ansicht.</span><span class="sxs-lookup"><span data-stu-id="b166d-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="b166d-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="b166d-274">**Export**:</span></span>

<span data-ttu-id="b166d-275">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="b166d-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b166d-276">Wenn Sie also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="b166d-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b166d-277">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b166d-278">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="b166d-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b166d-279">Richtungs Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b166d-280">Trichter Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b166d-281">In der **Trichter** Ansicht erfahren Sie, wie die e-Mail-Bedrohungsschutz Funktionen von Microsoft eingehende und ausgehende e-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="b166d-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b166d-282">Es enthält Details zur Gesamtzahl der e-Mails und dazu, wie die konfigurierten Funktionen zum Schutz vor Bedrohungen, einschließlich Edgeschutz, Antischadsoftware, AntiPhishing, Antispam-und Antispoofing diese Anzahl beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="b166d-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b166d-283">Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="b166d-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b166d-284">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="b166d-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b166d-285">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="b166d-285">**Direction**:</span></span>

  - <span data-ttu-id="b166d-286">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-286">**Inbound**</span></span>
  - <span data-ttu-id="b166d-287">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-287">**Outbound**</span></span>
  - <span data-ttu-id="b166d-288">**Intra-org**: diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; Das heißt, Absender-ABC@Domain.com sendet an den Empfänger XYZ@Domain.com (separat von eingehend und ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="b166d-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b166d-289">Die Ansicht aggregierte Ansicht und Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="b166d-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b166d-290">Wenn Sie auf **Filter** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="b166d-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b166d-291">Dieses Diagramm zeigt die Anzahl der e-Mail-Nachweise:</span><span class="sxs-lookup"><span data-stu-id="b166d-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b166d-292">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="b166d-292">**Total email**</span></span>
- <span data-ttu-id="b166d-293">**E-Mail nach dem Edge-Schutz**</span><span class="sxs-lookup"><span data-stu-id="b166d-293">**Email after edge protection**</span></span>
- <span data-ttu-id="b166d-294">**E-Mail nach Anti-Malware, Datei Zuverlässigkeit, Dateityp Block**</span><span class="sxs-lookup"><span data-stu-id="b166d-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b166d-295">**E-Mail nach Anti-Phishing, URL-Reputation, Marken Identitätswechsel, Anti-Spoofing**</span><span class="sxs-lookup"><span data-stu-id="b166d-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b166d-296">**E-Mail nach Spam Schutz, Massen-e-Mail-Filterung**</span><span class="sxs-lookup"><span data-stu-id="b166d-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b166d-297">**E-Mail nach Benutzer-und Domänen Identitätswechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b166d-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="b166d-298">**E-Mail nach Datei-und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b166d-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="b166d-299">**E-Mail-Nachricht wurde nach dem Zustellungs Schutz als gutartig erkannt (URL-Klick-Zeit Schutz)**</span><span class="sxs-lookup"><span data-stu-id="b166d-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b166d-300"><sup>1</sup> Verteidiger nur für Office 365</span><span class="sxs-lookup"><span data-stu-id="b166d-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b166d-301">Wenn Sie die von EoP oder Defender gefilterte e-Mail für Office 365 separat anzeigen möchten, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="b166d-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b166d-302">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b166d-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b166d-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="b166d-303">**Date**</span></span>
- <span data-ttu-id="b166d-304">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="b166d-304">**Total email**</span></span>
- <span data-ttu-id="b166d-305">**Kantenschutz**</span><span class="sxs-lookup"><span data-stu-id="b166d-305">**Edge protection**</span></span>
- <span data-ttu-id="b166d-306">**Anti-Malware, Datei Zuverlässigkeit, Dateityp Block**:</span><span class="sxs-lookup"><span data-stu-id="b166d-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b166d-307">**Dateireputation**: Nachrichten, die aufgrund der Identifizierung einer angehängten Datei durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b166d-308">**Dateityp Block**: Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b166d-309">**Anti-Phishing, URL-Reputation, Marken Identitätswechsel, Spoofing**:</span><span class="sxs-lookup"><span data-stu-id="b166d-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b166d-310">**URL-Reputation**: Nachrichten, die aufgrund der Identifizierung der URL durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b166d-311">**Marken Identitätswechsel**: Nachrichten, die aufgrund der Nachricht aus bekannten Absender der Markenidentität gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b166d-312">**Anti-Spoof**: Nachrichten, die aufgrund der Nachricht gefiltert werden, die versucht, eine Domäne zu fälschen, zu der der Empfänger gehört, oder eine Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="b166d-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b166d-313">**Anti-Spam, Massen-e-Mail-Filterung**:</span><span class="sxs-lookup"><span data-stu-id="b166d-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b166d-314">**Massen-e-Mail-Filterung**: Nachrichten, die aufgrund eines Versuchs zur Zustellung von Massen-e-Mails an die Empfänger gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="b166d-315">**Benutzer-und Domänen Identitätswechsel (Verteidiger für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b166d-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b166d-316">**Benutzeridentitätswechsel**: Nachrichten, die aufgrund eines Versuchs zur Identitätswechsel eines Benutzers (Nachrichtenabsender) gefiltert wurden, der in den Identitätswechsel-Schutzeinstellungen einer Anti-Phishing-Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b166d-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b166d-317">**Domänen Identitätswechsel**: Nachrichten, die aufgrund eines Versuchs zur Identitätswechsel einer Domäne gefiltert wurden, die in den Identitätswechsel-Schutzeinstellungen einer Anti-Phishing-Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b166d-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b166d-318">**Datei-und URL-Detonation (Verteidiger für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b166d-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b166d-319">**Datei Explosion**: Nachrichten, die von einer Richtlinie für sichere Anlagen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="b166d-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b166d-320">**URL-Detonation**: Nachricht, gefiltert nach einer Richtlinie zu sicheren Links.</span><span class="sxs-lookup"><span data-stu-id="b166d-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b166d-321">**Schutz nach Zustellung und zap (ATP) oder zap (EoP)**: Zap gibt die automatische Bereinigung der Nullstunde an.</span><span class="sxs-lookup"><span data-stu-id="b166d-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="b166d-322">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der e-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b166d-323">**Export**:</span><span class="sxs-lookup"><span data-stu-id="b166d-323">**Export**:</span></span>

<span data-ttu-id="b166d-324">Nachdem Sie unter **Optionen** auf **exportieren** klicken, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="b166d-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b166d-325">**Zusammenfassung (höchstens mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="b166d-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b166d-326">**Details (höchstens mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="b166d-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b166d-327">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="b166d-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b166d-328">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b166d-329">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b166d-330">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="b166d-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b166d-331">Trichter Ansicht im Nachrichtenflussstatus Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b166d-332">Tech-Ansicht für den Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b166d-333">Die **Tech-Ansicht** ähnelt der **Trichter** Ansicht und bietet detailliertere Details für die konfigurierten Features zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="b166d-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b166d-334">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Stadien des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b166d-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b166d-335">Wenn Sie auf die Registerkarte **Tech-Ansicht** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="b166d-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b166d-336">**Datum**: die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="b166d-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b166d-337">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="b166d-337">**Direction**:</span></span>

  - <span data-ttu-id="b166d-338">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-338">**Inbound**</span></span>
  - <span data-ttu-id="b166d-339">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="b166d-339">**Outbound**</span></span>
  - <span data-ttu-id="b166d-340">**Intra-org**: diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="b166d-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b166d-341">Absender ABC@Domain.com wird an den Empfänger XYZ@Domain.com gesendet (separat von eingehend und ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="b166d-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b166d-342">Die Ansicht aggregierte Ansicht und Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="b166d-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b166d-343">Wenn Sie auf **Filter** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="b166d-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b166d-344">In diesem Diagramm werden Nachrichten angezeigt, die in die folgenden Kategorien aufgeteilt sind:</span><span class="sxs-lookup"><span data-stu-id="b166d-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b166d-345">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="b166d-345">**Total email**</span></span>
- <span data-ttu-id="b166d-346">**Edge-Allow** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="b166d-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b166d-347">**Keine Schadsoftware**, **Erkennung sicherer Anlagen** <sup>\*</sup> , Erkennung von **Anti-Malware-Engines** und **Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b166d-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="b166d-348">**Nicht Phishing**, **DMARC-Fehler**, **Identitätswechsel Erkennung**, **Spoof-Erkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="b166d-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b166d-349">**Keine Erkennung mit URL-Detonation** und **URL-detonations Erkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b166d-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b166d-350">**Nicht Spam** und  **Spam**</span><span class="sxs-lookup"><span data-stu-id="b166d-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b166d-351">**Nicht-böswillige e-Mails**, **Erkennung sicherer Links** <sup>\*</sup> und **zap**</span><span class="sxs-lookup"><span data-stu-id="b166d-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b166d-352"><sup>\*</sup> Verteidiger für Office 365</span><span class="sxs-lookup"><span data-stu-id="b166d-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b166d-353">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b166d-354">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b166d-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b166d-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="b166d-355">**Date**</span></span>
- <span data-ttu-id="b166d-356">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="b166d-356">**Total email**</span></span>
- <span data-ttu-id="b166d-357">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="b166d-357">**Edge filtered**</span></span>
- <span data-ttu-id="b166d-358">**Anti-Malware-Modul, sichere Anlagen, Regelfilter**:</span><span class="sxs-lookup"><span data-stu-id="b166d-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="b166d-359">**Regel gefiltert**: Nachrichten, die aufgrund von Nachrichtenfluss Regeln gefiltert wurden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="b166d-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b166d-360">**DMARC, Identitätswechsel, Spoofing, Phishing-Filterung**:</span><span class="sxs-lookup"><span data-stu-id="b166d-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="b166d-361">**DMARC**: Nachrichten, die aufgrund der Nachricht, deren DMARC-Authentifizierungsüberprüfung fehlgeschlagen ist, gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="b166d-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b166d-362">**URL-detonations Erkennung**</span><span class="sxs-lookup"><span data-stu-id="b166d-362">**URL detonation detection**</span></span>
- <span data-ttu-id="b166d-363">**Anti-Spam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="b166d-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b166d-364">**Zap entfernt**</span><span class="sxs-lookup"><span data-stu-id="b166d-364">**ZAP removed**</span></span>
- <span data-ttu-id="b166d-365">**Erkennung durch sichere Links**</span><span class="sxs-lookup"><span data-stu-id="b166d-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="b166d-366">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der e-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b166d-367">**Export**:</span><span class="sxs-lookup"><span data-stu-id="b166d-367">**Export**:</span></span>

<span data-ttu-id="b166d-368">Beim Klicken auf **exportieren** unter **Optionen** können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="b166d-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b166d-369">**Zusammenfassung (höchstens mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="b166d-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b166d-370">**Details (höchstens mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="b166d-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b166d-371">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="b166d-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b166d-372">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b166d-373">Jede exportierte CSV-Datei ist auf 150.000 Zeilen limitiert.</span><span class="sxs-lookup"><span data-stu-id="b166d-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b166d-374">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="b166d-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b166d-375">Tech-Ansicht im Nachrichtenfluss-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b166d-376">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="b166d-376">Sent and received email report</span></span>

<span data-ttu-id="b166d-377">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="b166d-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="b166d-378">Der Unterschied zwischen diesem Bericht und dem Nachrichten [Fluss Statusbericht](#mailflow-status-report) lautet: dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edge-Schutz blockiert wurden. Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="b166d-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="b166d-379">Die Aggregatansicht und die Detailansicht des Berichts erlauben eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="b166d-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="b166d-380">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie  zum \> **Dashboard** Berichte, und wählen Sie **gesendete und empfangene e-Mails** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="b166d-381">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="b166d-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendete und empfangene e-Mail-widget im Dashboard Berichte](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b166d-383">Berichtsansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="b166d-384">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b166d-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b166d-385">**Aufschlüsseln nach: Typ**: das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="b166d-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="b166d-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="b166d-386">**Total**</span></span>
  - <span data-ttu-id="b166d-387">**Gute e-Mail**</span><span class="sxs-lookup"><span data-stu-id="b166d-387">**Good mail**</span></span>
  - <span data-ttu-id="b166d-388">**Schadsoftware (Anti-Malware)** (EoP)</span><span class="sxs-lookup"><span data-stu-id="b166d-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="b166d-389">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="b166d-389">**Spam detections**</span></span>
  - <span data-ttu-id="b166d-390">**Regel Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b166d-390">**Rule messages**</span></span>
  - <span data-ttu-id="b166d-391">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="b166d-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="b166d-392">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Geben Sie Ansicht im Bericht gesendete und empfangene e-Mails ein.](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="b166d-394">**Aufschlüsseln nach: Direction**: das Diagramm zeigt **Gesamt**-, **eingehende** und **ausgehende** Daten.</span><span class="sxs-lookup"><span data-stu-id="b166d-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="b166d-395">Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für diesen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungs Ansicht im Bericht "gesendete und empfangene e-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="b166d-397">**Drilldown nach** \> **Schadsoftware (Anti-Malware)**: mit dieser Auswahl gelangen Sie zur [Malware Erkennung in e-Mail-Bericht](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="b166d-398">**Drilldown nach** \> **Spamerkennungen)**: mit dieser Auswahl gelangen Sie zum [Spam Erkennungs Bericht](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b166d-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b166d-399">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="b166d-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b166d-400">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b166d-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="b166d-401">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="b166d-401">Direction values</span></span>
- <span data-ttu-id="b166d-402">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="b166d-402">Type values</span></span>

<span data-ttu-id="b166d-403">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b166d-404">Detailtabellen Ansicht für den gesendeten und empfangenen e-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="b166d-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="b166d-405">Wenn Sie auf **Tabelle Details anzeigen** in der Ansicht **aufschlüsseln nach: Richtung** oder **aufschlüsseln nach: Richtungs** Ansicht klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b166d-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="b166d-406">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b166d-406">**Date (UTC)**</span></span>
- <span data-ttu-id="b166d-407">**Type**</span><span class="sxs-lookup"><span data-stu-id="b166d-407">**Type**</span></span>
- <span data-ttu-id="b166d-408">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="b166d-408">**Direction**</span></span>
- <span data-ttu-id="b166d-409">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="b166d-409">**Message count**</span></span>

<span data-ttu-id="b166d-410">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="b166d-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b166d-411">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b166d-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="b166d-412">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="b166d-412">Direction values</span></span>
- <span data-ttu-id="b166d-413">Type-Werte</span><span class="sxs-lookup"><span data-stu-id="b166d-413">Type values</span></span>

<span data-ttu-id="b166d-414">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="b166d-415">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="b166d-415">Top senders and recipients report</span></span>

<span data-ttu-id="b166d-416">Der Bericht " **oberster Absender und Empfänger** " ist ein Kreisdiagramm, in dem Ihre oberen e-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b166d-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="b166d-417">Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **oberste Absender und Empfänger** aus.</span><span class="sxs-lookup"><span data-stu-id="b166d-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="b166d-418">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="b166d-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Top-Absender und Empfänger-Widget im Dashboard Berichte](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b166d-420">Berichtsansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="b166d-421">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b166d-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b166d-422">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="b166d-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="b166d-423">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="b166d-424">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="b166d-425">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="b166d-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="b166d-426">**Daten für \> Top-Schadsoftware-Empfänger anzeigen (Verteidiger für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b166d-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="b166d-427">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="b166d-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="b166d-428">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b166d-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="b166d-429">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "obere Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b166d-431">Detailtabellen Ansicht für den oberen Absender und Empfängerbericht</span><span class="sxs-lookup"><span data-stu-id="b166d-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="b166d-432">Wenn Sie auf **Detailtabelle anzeigen** klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="b166d-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b166d-433">**Anzeigen von Daten für \> Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="b166d-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="b166d-434">**Top-e-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="b166d-434">**Top mail senders**</span></span>
  - <span data-ttu-id="b166d-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-435">**Count**</span></span>

- <span data-ttu-id="b166d-436">**Anzeigen von Daten für \> Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="b166d-437">**Top-e-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="b166d-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-438">**Count**</span></span>

- <span data-ttu-id="b166d-439">**Anzeigen von Daten für \> Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="b166d-440">**Top-Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="b166d-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-441">**Count**</span></span>

- <span data-ttu-id="b166d-442">**Daten anzeigen für \> Top-Schadsoftware-Empfänger** (EoP)</span><span class="sxs-lookup"><span data-stu-id="b166d-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="b166d-443">**Top-Schadsoftware-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b166d-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="b166d-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-444">**Count**</span></span>

- <span data-ttu-id="b166d-445">**Daten für \> Top-Schadsoftware-Empfänger anzeigen (Verteidiger für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b166d-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="b166d-446">**Top-Schadsoftware-Empfänger (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b166d-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="b166d-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="b166d-447">**Count**</span></span>

<span data-ttu-id="b166d-448">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="b166d-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b166d-449">Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b166d-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b166d-450">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="b166d-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b166d-451">Damit Sie die in diesem Artikel beschriebenen Berichte anzeigen und verwenden können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="b166d-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b166d-452">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="b166d-452">**Organization Management**</span></span>
- <span data-ttu-id="b166d-453">**Sicherheits Administrator**</span><span class="sxs-lookup"><span data-stu-id="b166d-453">**Security Administrator**</span></span>
- <span data-ttu-id="b166d-454">**Sicherheits Leser**</span><span class="sxs-lookup"><span data-stu-id="b166d-454">**Security Reader**</span></span>
- <span data-ttu-id="b166d-455">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="b166d-455">**Global Reader**</span></span>

<span data-ttu-id="b166d-456">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b166d-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b166d-457">**Hinweis**: beim Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b166d-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b166d-458">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b166d-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b166d-459">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b166d-459">Related topics</span></span>

[<span data-ttu-id="b166d-460">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b166d-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b166d-461">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b166d-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="b166d-462">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b166d-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b166d-463">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="b166d-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
