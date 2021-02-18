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
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286717"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="f3659-103">Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f3659-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3659-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f3659-104">**Applies to**</span></span>
- [<span data-ttu-id="f3659-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3659-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3659-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f3659-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f3659-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3659-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f3659-108">Zusätzlich zu den Nachrichtenflussberichten, [](mail-flow-insights-v2.md) die im E-Mail-Flussdashboard im Security & Compliance Center verfügbar sind, stehen im Dashboard "Berichte" verschiedene zusätzliche Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="f3659-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="f3659-109">Wenn Sie über die erforderlichen [Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im [Security & Compliance Center](https://protection.office.com) anzeigen, indem Sie zum Dashboard **"Berichte"** \> **gehen.**</span><span class="sxs-lookup"><span data-stu-id="f3659-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f3659-110">Um direkt zum Dashboard "Berichte" zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="f3659-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="f3659-112">Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-112">Connector report</span></span>

<span data-ttu-id="f3659-113">Der **Connectorbericht zeigt** nachrichtenflussaktivitäten auf den eingehenden und ausgehenden [Connectors,](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f3659-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="f3659-114">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  den **Connectorbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="f3659-115">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="f3659-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorberichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="f3659-117">Berichtsansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-117">Report view for the Connector report</span></span>

<span data-ttu-id="f3659-118">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f3659-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="f3659-119">**Daten anzeigen nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, organisiert nach:</span><span class="sxs-lookup"><span data-stu-id="f3659-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="f3659-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="f3659-120">**Total**</span></span>
  - <span data-ttu-id="f3659-121">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f3659-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f3659-122">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f3659-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f3659-123">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f3659-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="f3659-124">Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine dieser Optionen oder den **ganzen Nachrichtenfluss auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="f3659-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach Nachrichtenfluss im Connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="f3659-126">**Daten nach: TLS-Verwendung anzeigen:** Dieses Diagramm zeigt den Prozentsatz der Verwendung der Transport Layer Security (TLS)-Version für den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="f3659-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="f3659-127">Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine der folgenden Optionen auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="f3659-128">**Sämtlicher Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="f3659-128">**All mail flow**</span></span>
  - <span data-ttu-id="f3659-129">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f3659-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f3659-130">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="f3659-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f3659-131">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f3659-131">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach der Verwendung von TLS im Connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="f3659-133">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="f3659-134">Detailtabelle für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-134">Details table view for the Connector report</span></span>

<span data-ttu-id="f3659-135">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3659-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f3659-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3659-136">**Date**</span></span>
- <span data-ttu-id="f3659-137">**Connectorrichtung und -name**</span><span class="sxs-lookup"><span data-stu-id="f3659-137">**Connector direction and name**</span></span>
- <span data-ttu-id="f3659-138">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="f3659-138">**Connector type**</span></span>
- <span data-ttu-id="f3659-139">**Erzwungenes TLS?**: Der Wert **True** oder **False**.</span><span class="sxs-lookup"><span data-stu-id="f3659-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="f3659-140">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f3659-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="f3659-141">**TLS 1.0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f3659-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="f3659-142">**TLS 1.1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f3659-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="f3659-143">**TLS 1.2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="f3659-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="f3659-144">**Volume**: Die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f3659-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="f3659-145">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3659-146">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f3659-147">Bericht über Exchange-Transportregel</span><span class="sxs-lookup"><span data-stu-id="f3659-147">Exchange transport rule report</span></span>

<span data-ttu-id="f3659-148">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf eingehende und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f3659-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f3659-149">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  die **Exchange-Transportregel aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="f3659-150">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="f3659-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f3659-152">Berichtsansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="f3659-153">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f3659-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="f3659-154">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Folgendem: Richtung:** Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="f3659-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="f3659-155">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Schweregrad aufbrechen:** Dieses Diagramm  zeigt die Anzahl der Nachrichten mit hohem schweregrad und mittlerem Schweregrad und niedrigem **Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="f3659-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f3659-156">Sie legen den Schweregrad als Aktion in der Regel **(Diese** Regel mit Schweregrad oder _SetAuditSeverity überwachen) festgelegt._</span><span class="sxs-lookup"><span data-stu-id="f3659-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f3659-157">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="f3659-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f3659-158">**Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Nach Folgendem:** Richtung: Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="f3659-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="f3659-159">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f3659-160">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="f3659-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f3659-161">**Anzeigen von Daten für: Gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f3659-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f3659-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f3659-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="f3659-163">**Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Aufbrechen nach: Richtung:** Diese Ansicht zeigt die Anzahl der  Nachrichten mit hohem schweregrad und mittlerem Schweregrad sowie Nachrichten mit niedrigem Schweregrad, die von den DLP-Transportregeln betroffen waren. </span><span class="sxs-lookup"><span data-stu-id="f3659-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="f3659-164">Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f3659-165">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="f3659-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f3659-166">**Anzeigen von Daten für: Gefährdete Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f3659-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f3659-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f3659-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="f3659-168">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f3659-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="f3659-169">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f3659-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3659-170">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f3659-170">Direction values</span></span>
- <span data-ttu-id="f3659-171">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="f3659-171">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f3659-173">Detailtabelle für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="f3659-174">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="f3659-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f3659-175">**Anzeigen von Daten nach: Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="f3659-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="f3659-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3659-176">**Date**</span></span>
  - <span data-ttu-id="f3659-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f3659-177">**Transport rule**</span></span>
  - <span data-ttu-id="f3659-178">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f3659-178">**Subject**</span></span>
  - <span data-ttu-id="f3659-179">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f3659-179">**Sender address**</span></span>
  - <span data-ttu-id="f3659-180">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f3659-180">**Recipient address**</span></span>
  - <span data-ttu-id="f3659-181">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="f3659-181">**Severity**</span></span>
  - <span data-ttu-id="f3659-182">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="f3659-182">**Direction**</span></span>

- <span data-ttu-id="f3659-183">**Anzeigen von Daten nach: DLP Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="f3659-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="f3659-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3659-184">**Date**</span></span>
  - <span data-ttu-id="f3659-185">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="f3659-185">**DLP policy**</span></span>
  - <span data-ttu-id="f3659-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f3659-186">**Transport rule**</span></span>
  - <span data-ttu-id="f3659-187">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f3659-187">**Subject**</span></span>
  - <span data-ttu-id="f3659-188">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f3659-188">**Sender address**</span></span>
  - <span data-ttu-id="f3659-189">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f3659-189">**Recipient address**</span></span>
  - <span data-ttu-id="f3659-190">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="f3659-190">**Severity**</span></span>
  - <span data-ttu-id="f3659-191">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="f3659-191">**Direction**</span></span>

<span data-ttu-id="f3659-192">Wenn Sie in einer **Detailtabelle auf** "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f3659-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3659-193">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f3659-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3659-194">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f3659-194">Direction values</span></span>
- <span data-ttu-id="f3659-195">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="f3659-195">Severity values</span></span>

<span data-ttu-id="f3659-196">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f3659-197">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-197">Forwarding report</span></span>

<span data-ttu-id="f3659-198">Der **Weiterleitungsbericht zeigt** die automatisch von Exchange Online-Postfächern an externe Domänen weitergeleiteten Nachrichten Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f3659-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="f3659-199">Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein gefährdetes Konto hinweisen.</span><span class="sxs-lookup"><span data-stu-id="f3659-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="f3659-200">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  **"Weiterleitungsbericht" aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="f3659-201">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="f3659-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget für Weiterleitungsbericht im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="f3659-203">Berichtsansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="f3659-204">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f3659-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3659-205">**Daten für: Weiterleitungsmethoden anzeigen:** Die folgenden Methoden werden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3659-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="f3659-206">**Transportregel:** Auch als [Nachrichtenflussregeln bezeichnet.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="f3659-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="f3659-207">**Postfachregel:** Auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="f3659-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="f3659-209">**Daten anzeigen für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.</span><span class="sxs-lookup"><span data-stu-id="f3659-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Domänen weiterleiten" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="f3659-211">**Anzeigen von Daten für: Weiterleitungen:** Die folgenden Weiterleitungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3659-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="f3659-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f3659-212">**Transport rule**</span></span>
  - <span data-ttu-id="f3659-213">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="f3659-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Weiterleitungsansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="f3659-215">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="f3659-216">Detailtabelle für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="f3659-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="f3659-217">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3659-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f3659-218">**Weiterleitungen:** Der Wert **der Transportregel** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="f3659-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="f3659-219">**Weiterleitungstyp:** Der Wert **Postfachregel oder** **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="f3659-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="f3659-220">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="f3659-220">**Recipient name**</span></span>
- <span data-ttu-id="f3659-221">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="f3659-221">**Recipient domain**</span></span>
- <span data-ttu-id="f3659-222">**Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="f3659-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="f3659-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-223">**Count**</span></span>
- <span data-ttu-id="f3659-224">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="f3659-224">**First forward date**</span></span>

<span data-ttu-id="f3659-225">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3659-226">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f3659-227">Statusbericht über den Nachrichtenfluss</span><span class="sxs-lookup"><span data-stu-id="f3659-227">Mailflow status report</span></span>

<span data-ttu-id="f3659-228">Der **Statusbericht "E-Mail-Nachrichtenfluss"** ähnelt dem Bericht "Gesendete und empfangene E-Mail", [](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die auf dem Edge zulässig oder blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3659-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f3659-229">Dies ist der einzige Bericht, der Informationen zum Edgeschutz enthält und zeigt, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f3659-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f3659-230">Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="f3659-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="f3659-231">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Berichtsdashboard, und wählen Sie den Statusbericht für den  \>  **Nachrichtenfluss aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="f3659-232">Um direkt zum Statusbericht für den **Nachrichtenfluss zu wechseln,** öffnen Sie <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="f3659-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Bericht "E-Mail-Statusbericht" im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3659-234">Typansicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f3659-235">Wenn Sie den Bericht öffnen, ist die Registerkarte **"Typ"** standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f3659-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f3659-236">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f3659-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3659-237">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="f3659-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="f3659-238">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="f3659-238">**Direction**:</span></span>

  - <span data-ttu-id="f3659-239">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f3659-239">**Inbound**</span></span>
  - <span data-ttu-id="f3659-240">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="f3659-240">**Outbound**</span></span>
  - <span data-ttu-id="f3659-241">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="f3659-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f3659-242">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von **ein-** und ausgehend **gezählt)**</span><span class="sxs-lookup"><span data-stu-id="f3659-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="f3659-243">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="f3659-243">**Type**:</span></span>

  - <span data-ttu-id="f3659-244">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-244">**Good mail**</span></span>
  - <span data-ttu-id="f3659-245">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="f3659-245">**Malware**</span></span>
  - <span data-ttu-id="f3659-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="f3659-246">**Spam**</span></span>
  - <span data-ttu-id="f3659-247">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="f3659-247">**Edge protection**</span></span>
  - <span data-ttu-id="f3659-248">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f3659-248">**Rule messages**</span></span>
  - <span data-ttu-id="f3659-249">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-249">**Phishing email**</span></span>

<span data-ttu-id="f3659-250">Das Diagramm ist nach den **Typwerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="f3659-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f3659-251">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="f3659-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f3659-252">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f3659-252">The data table contains the following information:</span></span>

- <span data-ttu-id="f3659-253">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="f3659-253">**Direction**</span></span>
- <span data-ttu-id="f3659-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="f3659-254">**Type**</span></span>
- <span data-ttu-id="f3659-255">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="f3659-255">**24 hours**</span></span>
- <span data-ttu-id="f3659-256">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="f3659-256">**3 days**</span></span>
- <span data-ttu-id="f3659-257">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="f3659-257">**7 days**</span></span>
- <span data-ttu-id="f3659-258">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="f3659-258">**15 days**</span></span>
- <span data-ttu-id="f3659-259">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="f3659-259">**30 days**</span></span>

<span data-ttu-id="f3659-260">Wenn Sie **auf "Kategorie auswählen" klicken,** um weitere Informationen zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f3659-261">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f3659-262">**Schadsoftware in** E-Mail: Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f3659-263">**Spamerkennungen:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f3659-264">**Edge blockierter Spam:** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f3659-265">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="f3659-265">**Export**:</span></span>

<span data-ttu-id="f3659-266">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="f3659-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f3659-267">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f3659-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f3659-268">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f3659-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3659-269">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3659-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f3659-270">Typansicht im Statusbericht "Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3659-271">Richtungsansicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f3659-272">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden dieselben Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3659-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f3659-273">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="f3659-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f3659-274">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="f3659-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="f3659-275">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3659-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f3659-276">Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="f3659-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f3659-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="f3659-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="f3659-278">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="f3659-278">**Export**:</span></span>

<span data-ttu-id="f3659-279">Für die Detailansicht können Sie Daten nur für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="f3659-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f3659-280">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f3659-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f3659-281">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f3659-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3659-282">Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3659-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f3659-283">Richtungsansicht im Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3659-284">Trichteransicht für den Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f3659-285">Die **Trichteransicht** zeigt, wie die Features zum Schutz vor E-Mail-Bedrohungen von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="f3659-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f3659-286">Sie enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfunktionen, einschließlich Edgeschutz, Ansoftware, Antiphishing, Antispam und Antis spoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="f3659-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="f3659-287">Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f3659-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3659-288">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="f3659-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f3659-289">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="f3659-289">**Direction**:</span></span>

  - <span data-ttu-id="f3659-290">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f3659-290">**Inbound**</span></span>
  - <span data-ttu-id="f3659-291">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="f3659-291">**Outbound**</span></span>
  - <span data-ttu-id="f3659-292">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. absender abc@domain.com an empfänger-xyz@domain.com (separat von ein- und ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="f3659-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f3659-293">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="f3659-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3659-294">Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="f3659-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f3659-295">Dieses Diagramm zeigt die Anzahl der E-Mails, organisiert nach:</span><span class="sxs-lookup"><span data-stu-id="f3659-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f3659-296">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-296">**Total email**</span></span>
- <span data-ttu-id="f3659-297">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="f3659-297">**Email after edge protection**</span></span>
- <span data-ttu-id="f3659-298">**E-Mail nach Ansoftware, Datei-Reputation, Dateitypblock**</span><span class="sxs-lookup"><span data-stu-id="f3659-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f3659-299">**E-Mail nach Anti phish, URL-Reputation, Markenwechsel, Antis spoofing**</span><span class="sxs-lookup"><span data-stu-id="f3659-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f3659-300">**E-Mail nach Antispam, Massen-E-Mail-Filterung**</span><span class="sxs-lookup"><span data-stu-id="f3659-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f3659-301">**E-Mail nach Benutzer- und Domänenwechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3659-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="f3659-302">**E-Mail nach Datei- und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3659-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="f3659-303">**E-Mail, die nach dem Schutz nach der Zustellung als gutartig erkannt wurde (URL-Klickzeitschutz)**</span><span class="sxs-lookup"><span data-stu-id="f3659-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f3659-304"><sup>Nur 1</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f3659-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f3659-305">Um die von EOP oder Defender für Office 365 gefilterte E-Mail separat anzeigen zu können, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="f3659-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f3659-306">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="f3659-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f3659-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3659-307">**Date**</span></span>
- <span data-ttu-id="f3659-308">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-308">**Total email**</span></span>
- <span data-ttu-id="f3659-309">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="f3659-309">**Edge protection**</span></span>
- <span data-ttu-id="f3659-310">**An malware, file reputation, file type block**:</span><span class="sxs-lookup"><span data-stu-id="f3659-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="f3659-311">**Datei-Reputation:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei durch andere Kunden von Microsoft gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="f3659-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="f3659-312">**Dateitypblock:** Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="f3659-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f3659-313">**Anti phish, URL reputation, Brand impersonation, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="f3659-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="f3659-314">**URL-Reputation:** Nachrichten, die aufgrund der Identifizierung der URL durch andere Kunden von Microsoft gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="f3659-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="f3659-315">**Markenwechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Marken imitierenden Absendern stammt.</span><span class="sxs-lookup"><span data-stu-id="f3659-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="f3659-316">**Antis spoof:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne, der der Empfänger angehört, oder eine Domäne zu spoofieren, die dem Nachrichtensender nicht gehört.</span><span class="sxs-lookup"><span data-stu-id="f3659-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="f3659-317">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="f3659-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="f3659-318">**Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs, Massen-E-Mails an die Empfänger zu senden, gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="f3659-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="f3659-319">**Identitätswechsel von Benutzern und Domänen (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="f3659-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f3659-320">**Benutzer-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, die Identität eines Benutzers (Nachrichtensenders) zu imitieren, der in den Identitätsschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f3659-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="f3659-321">**Domänen-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f3659-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="f3659-322">**Datei- und URL-Detonation (Defender für Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f3659-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f3659-323">**Dateidetonation:** Nachrichten, die durch eine Richtlinie für sichere Anlagen gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="f3659-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="f3659-324">**URL-Detonation:** Nachricht, gefiltert durch eine Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f3659-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="f3659-325">**Post delivery protection and ZAP (ATP) or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span><span class="sxs-lookup"><span data-stu-id="f3659-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="f3659-326">Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Zähler im Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f3659-327">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="f3659-327">**Export**:</span></span>

<span data-ttu-id="f3659-328">Nachdem Sie unter **"Optionen"** **auf**"Exportieren" geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f3659-329">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="f3659-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f3659-330">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="f3659-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f3659-331">Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="f3659-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f3659-332">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="f3659-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f3659-333">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f3659-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3659-334">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3659-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f3659-335">Trichteransicht im Statusbericht "E-Mail-Nachrichtenfluss"</span><span class="sxs-lookup"><span data-stu-id="f3659-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3659-336">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="f3659-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f3659-337">Die **tech-Ansicht** ähnelt der **Trichteransicht** und bietet genauere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="f3659-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f3659-338">Anhand des Diagramms können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f3659-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f3659-339">Wenn Sie auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f3659-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3659-340">**Datum**: Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="f3659-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f3659-341">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="f3659-341">**Direction**:</span></span>

  - <span data-ttu-id="f3659-342">**Eingehende Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f3659-342">**Inbound**</span></span>
  - <span data-ttu-id="f3659-343">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="f3659-343">**Outbound**</span></span>
  - <span data-ttu-id="f3659-344">**Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="f3659-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f3659-345">Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von ein- und ausgehend gezählt)</span><span class="sxs-lookup"><span data-stu-id="f3659-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f3659-346">Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="f3659-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3659-347">Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="f3659-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f3659-348">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="f3659-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f3659-349">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-349">**Total email**</span></span>
- <span data-ttu-id="f3659-350">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="f3659-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="f3659-351">**Keine Schadsoftware,** **Erkennung sicherer Anlagen,** Erkennung von An <sup>\*</sup> **malwaremodulen** und **Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f3659-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="f3659-352">**Kein Phishing,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishingerkennung**</span><span class="sxs-lookup"><span data-stu-id="f3659-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="f3659-353">**Keine Erkennung mit URL-Detonation** und **ERKENNUNG der URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f3659-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f3659-354">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="f3659-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="f3659-355">**Nicht schädliche E-Mails,** **Erkennung sicherer Links** und <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="f3659-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="f3659-356"><sup>\*</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f3659-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f3659-357">Wenn Sie mit der Maus auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f3659-358">Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="f3659-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f3659-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3659-359">**Date**</span></span>
- <span data-ttu-id="f3659-360">**Gesamt-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-360">**Total email**</span></span>
- <span data-ttu-id="f3659-361">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="f3659-361">**Edge filtered**</span></span>
- <span data-ttu-id="f3659-362">**An malware engine, Safe Attachments, rule filtered**:</span><span class="sxs-lookup"><span data-stu-id="f3659-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="f3659-363">**Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="f3659-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="f3659-364">**DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="f3659-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="f3659-365">**DMARC:** Nachrichten, die gefiltert wurden, weil die Nachricht die DMARC-Authentifizierungsprüfung nicht hat.</span><span class="sxs-lookup"><span data-stu-id="f3659-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="f3659-366">**Erkennung der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="f3659-366">**URL detonation detection**</span></span>
- <span data-ttu-id="f3659-367">**Antispamfilter**</span><span class="sxs-lookup"><span data-stu-id="f3659-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f3659-368">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="f3659-368">**ZAP removed**</span></span>
- <span data-ttu-id="f3659-369">**Erkennung durch sichere Links**</span><span class="sxs-lookup"><span data-stu-id="f3659-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="f3659-370">Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Zähler im Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f3659-371">**Exportieren:**</span><span class="sxs-lookup"><span data-stu-id="f3659-371">**Export**:</span></span>

<span data-ttu-id="f3659-372">Wenn Sie auf **"Exportieren"** **klicken,** können Sie unter "Optionen" einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="f3659-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f3659-373">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="f3659-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f3659-374">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="f3659-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f3659-375">Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="f3659-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f3659-376">Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="f3659-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f3659-377">Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f3659-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3659-378">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3659-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f3659-379">Tech view in the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="f3659-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f3659-380">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="f3659-380">Sent and received email report</span></span>

<span data-ttu-id="f3659-381">Der **Bericht "Gesendete** und empfangene E-Mail" ist ein intelligenter Bericht mit Informationen zu eingehenden und ausgehenden E-Mails, einschließlich Spamerkennungen, Schadsoftware und als "gut" gekennzeichneter E-Mails.</span><span class="sxs-lookup"><span data-stu-id="f3659-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="f3659-382">Der Unterschied zwischen diesem Bericht und [dem](#mailflow-status-report) Statusbericht für den Nachrichtenfluss besteht in folgendem: Dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="f3659-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="f3659-383">Die Aggregatansicht und die Detailansicht des Berichts lassen eine Filterung von 90 Tagen zu.</span><span class="sxs-lookup"><span data-stu-id="f3659-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3659-384">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie "Gesendete und empfangene E-Mail"  \>  **aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="f3659-385">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="f3659-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f3659-387">Berichtsansicht für den Bericht über gesendete und empfangene E-Mails</span><span class="sxs-lookup"><span data-stu-id="f3659-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="f3659-388">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f3659-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3659-389">**Aufteilen nach: Typ**: Das Diagramm zeigt alle verfügbaren Kategorien:</span><span class="sxs-lookup"><span data-stu-id="f3659-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="f3659-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="f3659-390">**Total**</span></span>
  - <span data-ttu-id="f3659-391">**Gute E-Mail**</span><span class="sxs-lookup"><span data-stu-id="f3659-391">**Good mail**</span></span>
  - <span data-ttu-id="f3659-392">**Schadsoftware (Ansoftware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f3659-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="f3659-393">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="f3659-393">**Spam detections**</span></span>
  - <span data-ttu-id="f3659-394">**Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f3659-394">**Rule messages**</span></span>
  - <span data-ttu-id="f3659-395">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="f3659-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="f3659-396">Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="f3659-398">**Aufbrechen nach: Richtung:** Das Diagramm zeigt **Die Gesamt-,** **Eingehenden** und **ausgehenden** Daten.</span><span class="sxs-lookup"><span data-stu-id="f3659-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="f3659-399">Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="f3659-401">**Drilldown nach** \> **Schadsoftware (Ansoftware):** Diese Auswahl führt Sie zu den [Schadsoftwareerkennungen im E-Mail-Bericht.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="f3659-402">**Drilldown nach** \> **Spamerkennungen):** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f3659-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f3659-403">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f3659-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3659-404">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f3659-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3659-405">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f3659-405">Direction values</span></span>
- <span data-ttu-id="f3659-406">Typwerte</span><span class="sxs-lookup"><span data-stu-id="f3659-406">Type values</span></span>

<span data-ttu-id="f3659-407">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f3659-408">Detailtabelle für den Bericht "Gesendete und empfangene E-Mail"</span><span class="sxs-lookup"><span data-stu-id="f3659-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="f3659-409">Wenn Sie in der **Tabelle "Details anzeigen"** in der Tabelle "Nach: Richtung oder Nach unten  **nach:** Richtungsansicht" klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3659-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="f3659-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f3659-410">**Date (UTC)**</span></span>
- <span data-ttu-id="f3659-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="f3659-411">**Type**</span></span>
- <span data-ttu-id="f3659-412">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="f3659-412">**Direction**</span></span>
- <span data-ttu-id="f3659-413">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f3659-413">**Message count**</span></span>

<span data-ttu-id="f3659-414">Wenn Sie in einer **Detailtabelle auf** "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f3659-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3659-415">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f3659-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3659-416">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="f3659-416">Direction values</span></span>
- <span data-ttu-id="f3659-417">Typwerte</span><span class="sxs-lookup"><span data-stu-id="f3659-417">Type values</span></span>

<span data-ttu-id="f3659-418">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f3659-419">Bericht zu den am besten verwendeten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="f3659-419">Top senders and recipients report</span></span>

<span data-ttu-id="f3659-420">Der **Bericht "Die besten Absender und Empfänger"** ist ein Kreisdiagramm, in dem Die besten E-Mail-Absender und Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3659-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="f3659-421">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie  \>  **"Top senders and recipients" aus.**</span><span class="sxs-lookup"><span data-stu-id="f3659-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="f3659-422">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="f3659-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Das Widget mit den besten Absendern und Empfängern im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f3659-424">Berichtsansicht für den Bericht der obersten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="f3659-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="f3659-425">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f3659-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3659-426">**Anzeigen von Daten für \> die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f3659-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="f3659-427">**Anzeigen von Daten für \> die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="f3659-428">**Anzeigen von Daten für \> die obersten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="f3659-429">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="f3659-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="f3659-430">**Anzeigen von Daten für \> die am besten geschützten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f3659-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="f3659-431">Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlen.</span><span class="sxs-lookup"><span data-stu-id="f3659-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="f3659-432">Wenn Sie im Kreisdiagramm auf einen Spalt zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3659-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="f3659-433">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in der Berichtsansicht im Bericht "Die obersten Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f3659-435">Detailtabelle für den Bericht der obersten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="f3659-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="f3659-436">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="f3659-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f3659-437">**Anzeigen von Daten für \> die obersten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f3659-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="f3659-438">**Die am besten verwendeten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="f3659-438">**Top mail senders**</span></span>
  - <span data-ttu-id="f3659-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-439">**Count**</span></span>

- <span data-ttu-id="f3659-440">**Anzeigen von Daten für \> die obersten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="f3659-441">**Die am besten verwendeten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="f3659-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-442">**Count**</span></span>

- <span data-ttu-id="f3659-443">**Anzeigen von Daten für \> die obersten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="f3659-444">**Die am besten erhaltenen Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="f3659-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-445">**Count**</span></span>

- <span data-ttu-id="f3659-446">**Anzeigen von Daten für \> EOP (Top Malware Recipients)**</span><span class="sxs-lookup"><span data-stu-id="f3659-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="f3659-447">**Am besten für Schadsoftwareempfänger**</span><span class="sxs-lookup"><span data-stu-id="f3659-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="f3659-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-448">**Count**</span></span>

- <span data-ttu-id="f3659-449">**Anzeigen von Daten für \> die am besten geschützten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f3659-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="f3659-450">**Am besten für Schadsoftwareempfänger (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f3659-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="f3659-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3659-451">**Count**</span></span>

<span data-ttu-id="f3659-452">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f3659-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3659-453">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f3659-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f3659-454">Welche Berechtigungen sind erforderlich, um diese Berichte anzeigen zu können?</span><span class="sxs-lookup"><span data-stu-id="f3659-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f3659-455">Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="f3659-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f3659-456">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="f3659-456">**Organization Management**</span></span>
- <span data-ttu-id="f3659-457">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="f3659-457">**Security Administrator**</span></span>
- <span data-ttu-id="f3659-458">**Sicherheitsleseprogramm**</span><span class="sxs-lookup"><span data-stu-id="f3659-458">**Security Reader**</span></span>
- <span data-ttu-id="f3659-459">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="f3659-459">**Global Reader**</span></span>

<span data-ttu-id="f3659-460">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f3659-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f3659-461">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3659-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f3659-462">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f3659-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3659-463">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f3659-463">Related topics</span></span>

[<span data-ttu-id="f3659-464">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f3659-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f3659-465">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f3659-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="f3659-466">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f3659-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f3659-467">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f3659-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
