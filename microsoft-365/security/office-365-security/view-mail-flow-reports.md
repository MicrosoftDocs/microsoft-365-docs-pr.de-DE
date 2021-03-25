---
title: Anzeigen von Nachrichtenflussberichten im Berichtedashboard
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
description: Administratoren können sich über die Nachrichtenflussberichte informieren, die im Dashboard Berichte im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13871908c3b09660906b9233d23495830cf31ba9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206234"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="22ec6-103">Anzeigen von Nachrichtenflussberichten im Berichtedashboard im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="22ec6-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="22ec6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="22ec6-104">**Applies to**</span></span>
- [<span data-ttu-id="22ec6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="22ec6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="22ec6-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="22ec6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="22ec6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22ec6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="22ec6-108">Zusätzlich zu den Nachrichtenflussberichten, [](mail-flow-insights-v2.md) die im Nachrichtenflussdashboard im Security & Compliance Center verfügbar sind, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenflussberichte zur Verfügung, mit deren Hilfe Sie Ihre Microsoft 365-Organisation überwachen können.</span><span class="sxs-lookup"><span data-stu-id="22ec6-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="22ec6-109">Wenn Sie über die [erforderlichen Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im [Security & Compliance Center](https://protection.office.com) anzeigen, indem Sie zu **Reports** \> **Dashboard gehen.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="22ec6-110">Öffnen Sie , um direkt zum Dashboard Berichte zu <https://protection.office.com/insightdashboard> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="22ec6-112">Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-112">Connector report</span></span>

<span data-ttu-id="22ec6-113">Der **Connectorbericht zeigt** nachrichtenflussaktivität auf den ein- und ausgehenden [Connectors,](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="22ec6-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="22ec6-114">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln **Sie** zu Berichtsdashboard, und wählen \>  Sie **Connectorbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="22ec6-115">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ConnectorReport> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorberichts-Widget im Berichtsdashboard](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="22ec6-117">Berichtsansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-117">Report view for the Connector report</span></span>

<span data-ttu-id="22ec6-118">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="22ec6-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="22ec6-119">**Daten anzeigen nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten an, die nach folgendem Geordneten organisiert sind:</span><span class="sxs-lookup"><span data-stu-id="22ec6-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="22ec6-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="22ec6-120">**Total**</span></span>
  - <span data-ttu-id="22ec6-121">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="22ec6-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="22ec6-122">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="22ec6-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="22ec6-123">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="22ec6-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="22ec6-124">Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement Daten für Steuerelement anzeigen, um eine dieser Optionen oder **Den ganzen Nachrichtenfluss auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach E-Mail-Fluss im Connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="22ec6-126">**Daten nach: TLS-Nutzung** anzeigen: Dieses Diagramm zeigt den Prozentsatz der Verwendung der Transport Layer Security (TLS)-Version für den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="22ec6-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="22ec6-127">Verwenden Sie zum Isolieren  der Daten im Diagramm die Option Daten für Steuerelement anzeigen, um eine der folgenden Optionen auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="22ec6-128">**Der ganze E-Mail-Fluss**</span><span class="sxs-lookup"><span data-stu-id="22ec6-128">**All mail flow**</span></span>
  - <span data-ttu-id="22ec6-129">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="22ec6-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="22ec6-130">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="22ec6-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="22ec6-131">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="22ec6-131">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Nutzung im Connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="22ec6-133">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="22ec6-134">Detailtabelle für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-134">Details table view for the Connector report</span></span>

<span data-ttu-id="22ec6-135">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22ec6-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="22ec6-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="22ec6-136">**Date**</span></span>
- <span data-ttu-id="22ec6-137">**Richtung und Name des Connectors**</span><span class="sxs-lookup"><span data-stu-id="22ec6-137">**Connector direction and name**</span></span>
- <span data-ttu-id="22ec6-138">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="22ec6-138">**Connector type**</span></span>
- <span data-ttu-id="22ec6-139">**Erzwungener TLS-Wert?**: Der **Wert True** oder **False**.</span><span class="sxs-lookup"><span data-stu-id="22ec6-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="22ec6-140">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="22ec6-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="22ec6-141">**TLS 1.0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="22ec6-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="22ec6-142">**TLS 1.1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="22ec6-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="22ec6-143">**TLS 1.2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="22ec6-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="22ec6-144">**Volume**: Die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="22ec6-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="22ec6-145">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="22ec6-146">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="22ec6-147">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-147">Exchange transport rule report</span></span>

<span data-ttu-id="22ec6-148">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf eingehende und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="22ec6-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="22ec6-149">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **Exchange-Transport-Regel aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="22ec6-150">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ETRRuleReport> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Berichtedashboard](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="22ec6-152">Berichtsansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="22ec6-153">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="22ec6-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="22ec6-154">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach: Richtung aufbrechen:** Dieses  Diagramm zeigt  die Anzahl der eingehenden und ausgehenden Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="22ec6-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="22ec6-155">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Aufbrechen nach: Schweregrad**: Dieses  Diagramm zeigt die Anzahl der Nachrichten mit hohem Schweregrad und mittlerem Schweregrad und niedriger **Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="22ec6-156">Sie legen den Schweregrad als Aktion in der Regel (**Diese** Regel mit schweregrad oder _SetAuditSeverity überwachen) festgelegt._</span><span class="sxs-lookup"><span data-stu-id="22ec6-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="22ec6-157">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="22ec6-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="22ec6-158">**Anzeigen von Daten nach: DLP Exchange-Transportregeln** \> **Nach: Richtung** aufbrechen: Dieses  Diagramm zeigt  die Anzahl der eingehenden und ausgehenden Nachrichten, die von DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="22ec6-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="22ec6-159">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="22ec6-160">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="22ec6-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="22ec6-161">**Anzeigen von Daten für: gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="22ec6-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="22ec6-162">**Anzeigen von Daten für: Geringes Inhaltsvolumen, das vom U.S. Patriot Act erkannt wurde**</span><span class="sxs-lookup"><span data-stu-id="22ec6-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="22ec6-163">**Anzeigen von Daten nach: DLP Exchange-Transportregeln** \> **Nach: Richtung** aufbrechen: Diese  Ansicht zeigt die Anzahl der  Nachrichten mit hohem schweregrad und mittlerem Schweregrad und niedriger Schweregrad, die von DLP-Transportregeln betroffen waren. </span><span class="sxs-lookup"><span data-stu-id="22ec6-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="22ec6-164">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="22ec6-165">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="22ec6-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="22ec6-166">**Anzeigen von Daten für: gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="22ec6-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="22ec6-167">**Anzeigen von Daten für: Geringes Inhaltsvolumen, das vom U.S. Patriot Act erkannt wurde**</span><span class="sxs-lookup"><span data-stu-id="22ec6-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="22ec6-168">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="22ec6-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="22ec6-169">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="22ec6-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="22ec6-170">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-170">Direction values</span></span>
- <span data-ttu-id="22ec6-171">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-171">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="22ec6-173">Detailtabelle für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="22ec6-174">Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="22ec6-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="22ec6-175">**Anzeigen von Daten nach: Exchange-Transport-Regeln**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="22ec6-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="22ec6-176">**Date**</span></span>
  - <span data-ttu-id="22ec6-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="22ec6-177">**Transport rule**</span></span>
  - <span data-ttu-id="22ec6-178">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="22ec6-178">**Subject**</span></span>
  - <span data-ttu-id="22ec6-179">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="22ec6-179">**Sender address**</span></span>
  - <span data-ttu-id="22ec6-180">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="22ec6-180">**Recipient address**</span></span>
  - <span data-ttu-id="22ec6-181">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="22ec6-181">**Severity**</span></span>
  - <span data-ttu-id="22ec6-182">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-182">**Direction**</span></span>

- <span data-ttu-id="22ec6-183">**Anzeigen von Daten nach: DLP Exchange-Transportregeln**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="22ec6-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="22ec6-184">**Date**</span></span>
  - <span data-ttu-id="22ec6-185">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="22ec6-185">**DLP policy**</span></span>
  - <span data-ttu-id="22ec6-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="22ec6-186">**Transport rule**</span></span>
  - <span data-ttu-id="22ec6-187">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="22ec6-187">**Subject**</span></span>
  - <span data-ttu-id="22ec6-188">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="22ec6-188">**Sender address**</span></span>
  - <span data-ttu-id="22ec6-189">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="22ec6-189">**Recipient address**</span></span>
  - <span data-ttu-id="22ec6-190">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="22ec6-190">**Severity**</span></span>
  - <span data-ttu-id="22ec6-191">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-191">**Direction**</span></span>

<span data-ttu-id="22ec6-192">Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="22ec6-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="22ec6-193">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="22ec6-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="22ec6-194">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-194">Direction values</span></span>
- <span data-ttu-id="22ec6-195">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-195">Severity values</span></span>

<span data-ttu-id="22ec6-196">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="22ec6-197">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-197">Forwarding report</span></span>

<span data-ttu-id="22ec6-198">Der **Weiterleitungsbericht zeigt** die automatisch weitergeleiteten Nachrichten Ihrer Organisation an externe Domänen aus Exchange Online-Postfächern an.</span><span class="sxs-lookup"><span data-stu-id="22ec6-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="22ec6-199">Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und möglicherweise auf ein gefährdetes Konto hinweisen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="22ec6-200">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **Weiterleitungsbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="22ec6-201">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=MailFlowForwarding> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleitungsberichts-Widget im Berichtsdashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="22ec6-203">Berichtsansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="22ec6-204">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="22ec6-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="22ec6-205">**Daten anzeigen für: Weiterleitungsmethoden**: Die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22ec6-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="22ec6-206">**Transportregel**: Wird auch als [Nachrichtenflussregeln bezeichnet.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="22ec6-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="22ec6-207">**Postfachregel**: Wird auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="22ec6-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Forwarding methods view in the Forwarding report](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="22ec6-209">**Daten anzeigen für: Weiterleitungsdomänen**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung sind.</span><span class="sxs-lookup"><span data-stu-id="22ec6-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Weiterleitungsdomänenansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="22ec6-211">**Daten anzeigen für: Forwarders**: Die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22ec6-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="22ec6-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="22ec6-212">**Transport rule**</span></span>
  - <span data-ttu-id="22ec6-213">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="22ec6-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Weiterleitungsansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="22ec6-215">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="22ec6-216">Detailtabelle für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="22ec6-217">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22ec6-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="22ec6-218">**Forwarders**: Der Wert **Transportregel** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="22ec6-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="22ec6-219">**Weiterleitungstyp**: Der Wert **Postfachregel oder** **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="22ec6-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="22ec6-220">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="22ec6-220">**Recipient name**</span></span>
- <span data-ttu-id="22ec6-221">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="22ec6-221">**Recipient domain**</span></span>
- <span data-ttu-id="22ec6-222">**Details**: Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="22ec6-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="22ec6-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-223">**Count**</span></span>
- <span data-ttu-id="22ec6-224">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="22ec6-224">**First forward date**</span></span>

<span data-ttu-id="22ec6-225">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="22ec6-226">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="22ec6-227">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-227">Mailflow status report</span></span>

<span data-ttu-id="22ec6-228">Der **E-Mailflow-Statusbericht** ähnelt dem Bericht "Gesendete und empfangene E-Mail", [](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die am Edge zulässig oder blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="22ec6-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="22ec6-229">Dies ist der einzige Bericht, der Edgeschutzinformationen enthält und zeigt, wie viele E-Mails blockiert werden, bevor sie von Exchange Online Protection (EOP) zur Auswertung in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="22ec6-230">Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="22ec6-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="22ec6-231">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **E-Mailflow-Statusbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="22ec6-232">Öffnen Sie , um direkt zum **Nachrichtenflussstatusbericht zu** <https://protection.office.com/mailflowStatusReport> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![E-Mailflow-Statusbericht-Widget im Berichtsdashboard](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="22ec6-234">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="22ec6-235">Wenn Sie den Bericht öffnen, **wird** standardmäßig die Registerkarte Typ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="22ec6-236">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="22ec6-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="22ec6-237">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="22ec6-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="22ec6-238">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-238">**Direction**:</span></span>

  - <span data-ttu-id="22ec6-239">**Eingehendes**</span><span class="sxs-lookup"><span data-stu-id="22ec6-239">**Inbound**</span></span>
  - <span data-ttu-id="22ec6-240">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="22ec6-240">**Outbound**</span></span>
  - <span data-ttu-id="22ec6-241">**Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="22ec6-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="22ec6-242">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von **ein-** und ausgehend **gezählt)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="22ec6-243">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-243">**Type**:</span></span>

  - <span data-ttu-id="22ec6-244">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="22ec6-244">**Good mail**</span></span>
  - <span data-ttu-id="22ec6-245">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="22ec6-245">**Malware**</span></span>
  - <span data-ttu-id="22ec6-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="22ec6-246">**Spam**</span></span>
  - <span data-ttu-id="22ec6-247">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="22ec6-247">**Edge protection**</span></span>
  - <span data-ttu-id="22ec6-248">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="22ec6-248">**Rule messages**</span></span>
  - <span data-ttu-id="22ec6-249">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="22ec6-249">**Phishing email**</span></span>

<span data-ttu-id="22ec6-250">Das Diagramm wird nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="22ec6-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="22ec6-251">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="22ec6-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="22ec6-252">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-252">The data table contains the following information:</span></span>

- <span data-ttu-id="22ec6-253">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-253">**Direction**</span></span>
- <span data-ttu-id="22ec6-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="22ec6-254">**Type**</span></span>
- <span data-ttu-id="22ec6-255">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="22ec6-255">**24 hours**</span></span>
- <span data-ttu-id="22ec6-256">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="22ec6-256">**3 days**</span></span>
- <span data-ttu-id="22ec6-257">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="22ec6-257">**7 days**</span></span>
- <span data-ttu-id="22ec6-258">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="22ec6-258">**15 days**</span></span>
- <span data-ttu-id="22ec6-259">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="22ec6-259">**30 days**</span></span>

<span data-ttu-id="22ec6-260">Wenn Sie auf **Kategorie auswählen klicken,** können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="22ec6-261">**Phishing-E-Mail:** Diese Auswahl führt Sie zum [Statusbericht zum Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="22ec6-262">**Schadsoftware in** E-Mail: Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="22ec6-263">**Spamerkennungen:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="22ec6-264">**Edge-blockierter Spam:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="22ec6-265">**Export**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-265">**Export**:</span></span>

<span data-ttu-id="22ec6-266">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="22ec6-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="22ec6-267">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="22ec6-268">Jede exportierte CSV-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="22ec6-269">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="22ec6-270">Typansicht im Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="22ec6-271">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="22ec6-272">Wenn Sie auf die **Registerkarte Richtung** klicken, werden dieselben Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="22ec6-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="22ec6-273">Das Diagramm wird nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="22ec6-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="22ec6-274">Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="22ec6-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="22ec6-275">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="22ec6-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="22ec6-276">Die Datentabelle enthält dieselben Informationen aus der **Type-Ansicht.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="22ec6-277">Die **Option Kategorie auswählen für weitere Details,** die auswahl- und verhalten verfügbar sind, sind mit der **Typansicht** identisch.</span><span class="sxs-lookup"><span data-stu-id="22ec6-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="22ec6-278">**Export**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-278">**Export**:</span></span>

<span data-ttu-id="22ec6-279">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="22ec6-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="22ec6-280">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="22ec6-281">Jede exportierte CSV-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="22ec6-282">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="22ec6-283">Richtungsansicht im Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="22ec6-284">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="22ec6-285">Die **Trichteransicht** zeigt, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="22ec6-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="22ec6-286">Sie enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Funktionen zum Schutz vor Bedrohungen, einschließlich Edgeschutz, Anschmierung von Schadsoftware, Antiphishing, Antispam und Antis spoofing auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="22ec6-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="22ec6-287">Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="22ec6-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="22ec6-288">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="22ec6-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="22ec6-289">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-289">**Direction**:</span></span>

  - <span data-ttu-id="22ec6-290">**Eingehendes**</span><span class="sxs-lookup"><span data-stu-id="22ec6-290">**Inbound**</span></span>
  - <span data-ttu-id="22ec6-291">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="22ec6-291">**Outbound**</span></span>
  - <span data-ttu-id="22ec6-292">**Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden. d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von ein- und ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="22ec6-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="22ec6-293">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="22ec6-294">Wenn Sie auf **Filtern** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="22ec6-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="22ec6-295">Dieses Diagramm zeigt die E-Mail-Anzahl, die nach folgendem Geordneten organisiert ist:</span><span class="sxs-lookup"><span data-stu-id="22ec6-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="22ec6-296">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="22ec6-296">**Total email**</span></span>
- <span data-ttu-id="22ec6-297">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="22ec6-297">**Email after edge protection**</span></span>
- <span data-ttu-id="22ec6-298">**E-Mail nach Anschmierung von Schadsoftware, Datei reputation, Dateitypblock**</span><span class="sxs-lookup"><span data-stu-id="22ec6-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="22ec6-299">**E-Mail nach Antiphish, URL-Reputation, Markenwechsel, Antis spoof**</span><span class="sxs-lookup"><span data-stu-id="22ec6-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="22ec6-300">**E-Mail nach Antispam, Massen-E-Mail-Filterung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="22ec6-301">**E-Mail nach Benutzer- und Domänenwechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="22ec6-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="22ec6-302">**E-Mail nach Datei- und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="22ec6-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="22ec6-303">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Klickzeitschutz)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="22ec6-304"><sup>Nur 1</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="22ec6-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="22ec6-305">Klicken Sie auf den Wert in der Diagrammlegende, um die von EOP oder Defender für Office 365 gefilterte E-Mail separat anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="22ec6-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="22ec6-306">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="22ec6-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="22ec6-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="22ec6-307">**Date**</span></span>
- <span data-ttu-id="22ec6-308">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="22ec6-308">**Total email**</span></span>
- <span data-ttu-id="22ec6-309">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="22ec6-309">**Edge protection**</span></span>
- <span data-ttu-id="22ec6-310">**An malware, file reputation, file type block**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="22ec6-311">**Datei-Reputation:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="22ec6-312">**Dateitypblock:** Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="22ec6-313">**Antiphish, URL-Reputation, Markenwechsel, Antis spoof**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="22ec6-314">**URL-Reputation:** Nachrichten, die aufgrund der Identifizierung der URL durch andere Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="22ec6-315">**Markenwechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Markensendern als Identitätswechsel gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="22ec6-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="22ec6-316">**Antis spoof**: Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder eine Domäne, die der Nachrichtensender nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="22ec6-317">**Antispam, Massen-E-Mail-Filterung**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="22ec6-318">Massen-E-Mail-Filterung: Nachrichten, die aufgrund eines Versuches gefiltert wurden, Massen-E-Mails an die Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="22ec6-319">Identitätswechsel von Benutzern und Domänen **(Defender für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="22ec6-320">**Benutzerwechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="22ec6-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="22ec6-321">**Domänenwechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="22ec6-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="22ec6-322">**Datei- und URL-Detonation (Defender für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="22ec6-323">**Dateidetonation:** Nachrichten, die nach einer Richtlinie für sichere Anlagen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="22ec6-324">**URL-Detonation:** Nachricht, die nach einer Richtlinie für sichere Links gefiltert wurde.</span><span class="sxs-lookup"><span data-stu-id="22ec6-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="22ec6-325">**Post-Delivery Protection und ZAP (ATP) oder ZAP (EOP):** ZAP gibt null Stunden automatisches Löschen an.</span><span class="sxs-lookup"><span data-stu-id="22ec6-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="22ec6-326">Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Anzahl im Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="22ec6-327">**Export**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-327">**Export**:</span></span>

<span data-ttu-id="22ec6-328">Nachdem Sie unter **Optionen** auf **Exportieren** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="22ec6-329">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="22ec6-330">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="22ec6-331">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="22ec6-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="22ec6-332">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="22ec6-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="22ec6-333">Jede exportierte CSV-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="22ec6-334">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="22ec6-335">Trichteransicht im Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="22ec6-336">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="22ec6-337">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Features zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="22ec6-338">Anhand des Diagramms können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="22ec6-339">Wenn Sie auf die Registerkarte **Tech-Ansicht** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="22ec6-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="22ec6-340">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="22ec6-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="22ec6-341">**Richtung**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-341">**Direction**:</span></span>

  - <span data-ttu-id="22ec6-342">**Eingehendes**</span><span class="sxs-lookup"><span data-stu-id="22ec6-342">**Inbound**</span></span>
  - <span data-ttu-id="22ec6-343">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="22ec6-343">**Outbound**</span></span>
  - <span data-ttu-id="22ec6-344">**Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="22ec6-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="22ec6-345">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von ein- und ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="22ec6-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="22ec6-346">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="22ec6-347">Wenn Sie auf **Filtern** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="22ec6-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="22ec6-348">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="22ec6-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="22ec6-349">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="22ec6-349">**Total email**</span></span>
- <span data-ttu-id="22ec6-350">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="22ec6-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="22ec6-351">**Keine Schadsoftware,** **Erkennung sicherer Anlagen,** <sup>\*</sup> Erkennung von An **malwaremodulen** und **Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="22ec6-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="22ec6-352">**Kein Phish,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishingerkennung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="22ec6-353">**Keine Erkennung mit URL-Detonation** und **URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="22ec6-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="22ec6-354">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="22ec6-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="22ec6-355">**Nicht schädliche E-Mails,** **Erkennung sicherer** <sup>\*</sup> Links und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="22ec6-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="22ec6-356"><sup>\*</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="22ec6-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="22ec6-357">Wenn Sie den Mauszeiger auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="22ec6-358">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="22ec6-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="22ec6-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="22ec6-359">**Date**</span></span>
- <span data-ttu-id="22ec6-360">**E-Mail insgesamt**</span><span class="sxs-lookup"><span data-stu-id="22ec6-360">**Total email**</span></span>
- <span data-ttu-id="22ec6-361">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="22ec6-361">**Edge filtered**</span></span>
- <span data-ttu-id="22ec6-362">**An malware engine, Safe Attachments, rule filtered**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="22ec6-363">**Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch als Transportregeln bekannt).</span><span class="sxs-lookup"><span data-stu-id="22ec6-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="22ec6-364">**DMARC, Identitätswechsel, Spoof, Phish gefiltert**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="22ec6-365">**DMARC**: Nachrichten, die gefiltert wurden, weil die DMARC-Authentifizierungsüberprüfung der Nachricht fehlt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="22ec6-366">**Erkennung der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="22ec6-366">**URL detonation detection**</span></span>
- <span data-ttu-id="22ec6-367">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="22ec6-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="22ec6-368">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="22ec6-368">**ZAP removed**</span></span>
- <span data-ttu-id="22ec6-369">**Erkennung durch sichere Links**</span><span class="sxs-lookup"><span data-stu-id="22ec6-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="22ec6-370">Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Anzahl im Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="22ec6-371">**Export**:</span><span class="sxs-lookup"><span data-stu-id="22ec6-371">**Export**:</span></span>

<span data-ttu-id="22ec6-372">Wenn Sie auf **Exportieren** klicken, können Sie unter **Optionen** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="22ec6-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="22ec6-373">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="22ec6-374">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="22ec6-375">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="22ec6-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="22ec6-376">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="22ec6-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="22ec6-377">Jede exportierte CSV-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="22ec6-378">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere CSV-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="22ec6-379">Tech-Ansicht im Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="22ec6-380">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-380">Sent and received email report</span></span>

<span data-ttu-id="22ec6-381">Der **Bericht "Gesendete** und empfangene E-Mail" ist ein smarter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails enthält, einschließlich Spamerkennungen, Schadsoftware und E-Mails, die als "gut" identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="22ec6-382">Der Unterschied zwischen diesem Bericht und dem [E-Mailflow-Statusbericht](#mailflow-status-report) ist: Dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="22ec6-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="22ec6-383">Die Aggregatansicht und die Detailansicht des Berichts ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="22ec6-384">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Gesendete und empfangene E-Mails aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="22ec6-385">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="22ec6-387">Berichtsansicht für den Gesendeten und empfangenen E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="22ec6-388">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="22ec6-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="22ec6-389">**Aufteilen nach: Typ**: Das Diagramm zeigt alle verfügbaren Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="22ec6-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="22ec6-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="22ec6-390">**Total**</span></span>
  - <span data-ttu-id="22ec6-391">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="22ec6-391">**Good mail**</span></span>
  - <span data-ttu-id="22ec6-392">**Schadsoftware (Anti-Malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="22ec6-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="22ec6-393">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="22ec6-393">**Spam detections**</span></span>
  - <span data-ttu-id="22ec6-394">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="22ec6-394">**Rule messages**</span></span>
  - <span data-ttu-id="22ec6-395">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="22ec6-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="22ec6-396">Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für den Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typansicht im Bericht Gesendete und empfangene E-Mail](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="22ec6-398">**Aufbrechen nach: Richtung**: Das Diagramm zeigt **Gesamt-,** **Eingehende** und **ausgehende** Daten an.</span><span class="sxs-lookup"><span data-stu-id="22ec6-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="22ec6-399">Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für den Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungsansicht im Bericht Gesendete und empfangene E-Mails](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="22ec6-401">**Drilldown von** \> **Schadsoftware (Ansoftware):** Diese Auswahl führt Sie zu den [Schadsoftwareerkennungen im E-Mail-Bericht.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="22ec6-402">**Drilldown von** \> **Spamerkennungen)**: Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="22ec6-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="22ec6-403">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="22ec6-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="22ec6-404">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="22ec6-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="22ec6-405">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-405">Direction values</span></span>
- <span data-ttu-id="22ec6-406">Typwerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-406">Type values</span></span>

<span data-ttu-id="22ec6-407">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="22ec6-408">Detailtabelle für den Gesendeten und empfangenen E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="22ec6-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="22ec6-409">Wenn Sie **in der Ansicht Nach:** Richtung oder Nach unten **nach:** Richtungsansicht auf Detailtabelle anzeigen klicken, werden die folgenden Informationen angezeigt: </span><span class="sxs-lookup"><span data-stu-id="22ec6-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="22ec6-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-410">**Date (UTC)**</span></span>
- <span data-ttu-id="22ec6-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="22ec6-411">**Type**</span></span>
- <span data-ttu-id="22ec6-412">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-412">**Direction**</span></span>
- <span data-ttu-id="22ec6-413">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="22ec6-413">**Message count**</span></span>

<span data-ttu-id="22ec6-414">Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="22ec6-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="22ec6-415">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="22ec6-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="22ec6-416">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-416">Direction values</span></span>
- <span data-ttu-id="22ec6-417">Typwerte</span><span class="sxs-lookup"><span data-stu-id="22ec6-417">Type values</span></span>

<span data-ttu-id="22ec6-418">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="22ec6-419">Bericht über die besten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="22ec6-419">Top senders and recipients report</span></span>

<span data-ttu-id="22ec6-420">Der **Bericht "Absender und Empfänger am** oberen Rand" ist ein Kreisdiagramm, in dem Ihre absender und empfänger am besten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="22ec6-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="22ec6-421">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Top senders and recipients aus.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="22ec6-422">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> wechseln.</span><span class="sxs-lookup"><span data-stu-id="22ec6-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget mit den besten Absendern und Empfängern im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="22ec6-424">Berichtsansicht für den Bericht mit den besten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="22ec6-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="22ec6-425">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="22ec6-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="22ec6-426">**Anzeigen von Daten für \> Die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="22ec6-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="22ec6-427">**Anzeigen von Daten für \> Die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="22ec6-428">**Anzeigen von Daten für \> Die besten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="22ec6-429">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="22ec6-430">**Anzeigen von Daten für \> Top Malware Recipients (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="22ec6-431">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlen.</span><span class="sxs-lookup"><span data-stu-id="22ec6-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="22ec6-432">Wenn Sie auf einen Keil im Kreisdiagramm zeigen, wird eine Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22ec6-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="22ec6-433">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "Absender und Empfänger am oberen Rand"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="22ec6-435">Detailtabelle für den Bericht "Absender und Empfänger am oberen Rand"</span><span class="sxs-lookup"><span data-stu-id="22ec6-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="22ec6-436">Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="22ec6-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="22ec6-437">**Anzeigen von Daten für \> Die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="22ec6-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="22ec6-438">**Die besten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="22ec6-438">**Top mail senders**</span></span>
  - <span data-ttu-id="22ec6-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-439">**Count**</span></span>

- <span data-ttu-id="22ec6-440">**Anzeigen von Daten für \> Die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="22ec6-441">**Die besten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="22ec6-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-442">**Count**</span></span>

- <span data-ttu-id="22ec6-443">**Anzeigen von Daten für \> Die besten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="22ec6-444">**Die besten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="22ec6-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="22ec6-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-445">**Count**</span></span>

- <span data-ttu-id="22ec6-446">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="22ec6-447">**Empfänger der besten Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="22ec6-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="22ec6-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-448">**Count**</span></span>

- <span data-ttu-id="22ec6-449">**Anzeigen von Daten für \> Top Malware Recipients (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="22ec6-450">**Top malware recipients (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="22ec6-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="22ec6-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="22ec6-451">**Count**</span></span>

<span data-ttu-id="22ec6-452">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="22ec6-453">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="22ec6-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="22ec6-454">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="22ec6-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="22ec6-455">Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="22ec6-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="22ec6-456">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="22ec6-456">**Organization Management**</span></span>
- <span data-ttu-id="22ec6-457">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="22ec6-457">**Security Administrator**</span></span>
- <span data-ttu-id="22ec6-458">**Security Reader**</span><span class="sxs-lookup"><span data-stu-id="22ec6-458">**Security Reader**</span></span>
- <span data-ttu-id="22ec6-459">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="22ec6-459">**Global Reader**</span></span>

<span data-ttu-id="22ec6-460">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="22ec6-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22ec6-461">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22ec6-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="22ec6-462">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="22ec6-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="22ec6-463">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="22ec6-463">Related topics</span></span>

[<span data-ttu-id="22ec6-464">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="22ec6-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="22ec6-465">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="22ec6-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="22ec6-466">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="22ec6-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="22ec6-467">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="22ec6-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
