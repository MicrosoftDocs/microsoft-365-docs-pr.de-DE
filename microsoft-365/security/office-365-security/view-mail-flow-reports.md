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
ms.openlocfilehash: fd8f6c3da1c195fbd540638ae73674deccf2762a
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985504"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="10c99-103">Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="10c99-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="10c99-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="10c99-104">**Applies to**</span></span>
- [<span data-ttu-id="10c99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="10c99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="10c99-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="10c99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="10c99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10c99-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="10c99-108">Zusätzlich zu den Nachrichtenflussberichten, die im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im Security & Compliance Center verfügbar sind, stehen im Berichtsdashboard eine Vielzahl zusätzlicher Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="10c99-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="10c99-109">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & [Compliance Center](https://protection.office.com) anzeigen, indem Sie zum **Berichtsdashboard** \> wechseln.</span><span class="sxs-lookup"><span data-stu-id="10c99-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="10c99-110">Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="10c99-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="10c99-112">Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-112">Connector report</span></span>

<span data-ttu-id="10c99-113">Der **Connectorbericht** zeigt Nachrichtenflussaktivitäten auf den [eingehenden und ausgehenden Connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="10c99-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="10c99-114">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Connectorbericht"** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="10c99-115">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="10c99-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorberichts-Widget im Berichtsdashboard](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="10c99-117">Berichtsansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-117">Report view for the Connector report</span></span>

<span data-ttu-id="10c99-118">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10c99-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="10c99-119">**Anzeigen von Daten nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten an, nach:</span><span class="sxs-lookup"><span data-stu-id="10c99-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="10c99-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="10c99-120">**Total**</span></span>
  - <span data-ttu-id="10c99-121">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="10c99-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="10c99-122">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="10c99-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="10c99-123">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="10c99-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="10c99-124">Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine dieser Optionen oder **den gesamten Nachrichtenfluss** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="10c99-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach E-Mail-Fluss im Connector-Bericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="10c99-126">**Anzeigen von Daten nach: TLS-Verwendung:** Dieses Diagramm zeigt den Prozentsatz der TLS-Versionsnutzung (Transport Layer Security) für den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="10c99-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="10c99-127">Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine der folgenden Optionen auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="10c99-128">**Alle Nachrichtenübermittlungen**</span><span class="sxs-lookup"><span data-stu-id="10c99-128">**All mail flow**</span></span>
  - <span data-ttu-id="10c99-129">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="10c99-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="10c99-130">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="10c99-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="10c99-131">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="10c99-131">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im Connector-Bericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="10c99-133">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="10c99-134">Detailtabellenansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-134">Details table view for the Connector report</span></span>

<span data-ttu-id="10c99-135">Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="10c99-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="10c99-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="10c99-136">**Date**</span></span>
- <span data-ttu-id="10c99-137">**Verbindungsrichtung und -name**</span><span class="sxs-lookup"><span data-stu-id="10c99-137">**Connector direction and name**</span></span>
- <span data-ttu-id="10c99-138">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="10c99-138">**Connector type**</span></span>
- <span data-ttu-id="10c99-139">**Tls erzwungen?**: Der Wert **True** oder **False**.</span><span class="sxs-lookup"><span data-stu-id="10c99-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="10c99-140">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="10c99-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="10c99-141">**TLS 1.0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="10c99-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="10c99-142">**TLS 1.1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="10c99-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="10c99-143">**TLS 1.2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="10c99-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="10c99-144">**Volume:** Die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="10c99-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="10c99-145">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="10c99-146">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="10c99-147">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-147">Exchange transport rule report</span></span>

<span data-ttu-id="10c99-148">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="10c99-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="10c99-149">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Exchange-Transportregel** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="10c99-150">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="10c99-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Berichtsdashboard](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="10c99-152">Berichtsansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="10c99-153">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10c99-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="10c99-154">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="10c99-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="10c99-155">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Schweregrad:** Dieses Diagramm zeigt die Anzahl der Meldungen mit **hohem und** **mittlerem Schweregrad** sowie Meldungen mit **dem niedrigen Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="10c99-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="10c99-156">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="10c99-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="10c99-157">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="10c99-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="10c99-158">**Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="10c99-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="10c99-159">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="10c99-160">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="10c99-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="10c99-161">**Anzeigen von Daten für: Kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="10c99-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="10c99-162">**Show data for: Low volume of content detected U.S. Mof Act**</span><span class="sxs-lookup"><span data-stu-id="10c99-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="10c99-163">**Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Diese Ansicht zeigt die Anzahl der Nachrichten mit **hohem und** **mittlerem Schweregrad** sowie Nachrichten mit **dem niedrigen Schweregrad,** die von DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="10c99-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="10c99-164">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="10c99-165">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="10c99-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="10c99-166">**Anzeigen von Daten für: Kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="10c99-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="10c99-167">**Show data for: Low volume of content detected U.S. Mof Act**</span><span class="sxs-lookup"><span data-stu-id="10c99-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="10c99-168">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="10c99-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="10c99-169">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="10c99-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="10c99-170">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="10c99-170">Direction values</span></span>
- <span data-ttu-id="10c99-171">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="10c99-171">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="10c99-173">Detailtabellenansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="10c99-174">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="10c99-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="10c99-175">**Anzeigen von Daten nach: Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="10c99-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="10c99-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="10c99-176">**Date**</span></span>
  - <span data-ttu-id="10c99-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="10c99-177">**Transport rule**</span></span>
  - <span data-ttu-id="10c99-178">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="10c99-178">**Subject**</span></span>
  - <span data-ttu-id="10c99-179">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="10c99-179">**Sender address**</span></span>
  - <span data-ttu-id="10c99-180">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="10c99-180">**Recipient address**</span></span>
  - <span data-ttu-id="10c99-181">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="10c99-181">**Severity**</span></span>
  - <span data-ttu-id="10c99-182">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="10c99-182">**Direction**</span></span>

- <span data-ttu-id="10c99-183">**Anzeigen von Daten nach: DLP Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="10c99-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="10c99-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="10c99-184">**Date**</span></span>
  - <span data-ttu-id="10c99-185">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="10c99-185">**DLP policy**</span></span>
  - <span data-ttu-id="10c99-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="10c99-186">**Transport rule**</span></span>
  - <span data-ttu-id="10c99-187">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="10c99-187">**Subject**</span></span>
  - <span data-ttu-id="10c99-188">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="10c99-188">**Sender address**</span></span>
  - <span data-ttu-id="10c99-189">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="10c99-189">**Recipient address**</span></span>
  - <span data-ttu-id="10c99-190">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="10c99-190">**Severity**</span></span>
  - <span data-ttu-id="10c99-191">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="10c99-191">**Direction**</span></span>

<span data-ttu-id="10c99-192">Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="10c99-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="10c99-193">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="10c99-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="10c99-194">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="10c99-194">Direction values</span></span>
- <span data-ttu-id="10c99-195">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="10c99-195">Severity values</span></span>

<span data-ttu-id="10c99-196">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="10c99-197">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-197">Forwarding report</span></span>

<span data-ttu-id="10c99-198">Der **Weiterleitungsbericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation aus Exchange Online-Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="10c99-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="10c99-199">Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein kompromittiertes Konto hinweisen.</span><span class="sxs-lookup"><span data-stu-id="10c99-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="10c99-200">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Weiterleitungsbericht"** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="10c99-201">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="10c99-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleitung des Berichts-Widgets im Berichtsdashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="10c99-203">Berichtsansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="10c99-204">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10c99-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="10c99-205">**Anzeigen von Daten für: Weiterleitungsmethoden:** Die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="10c99-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="10c99-206">**Transportregel**: Wird auch als [Nachrichtenflussregeln bezeichnet.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="10c99-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="10c99-207">**Postfachregel**: Wird auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="10c99-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="10c99-209">**Anzeigen von Daten für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.</span><span class="sxs-lookup"><span data-stu-id="10c99-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleitungsdomänen" im Bericht "Weiterleitung"](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="10c99-211">**Show data for: forwarders**: The following forwarders are shown:</span><span class="sxs-lookup"><span data-stu-id="10c99-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="10c99-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="10c99-212">**Transport rule**</span></span>
  - <span data-ttu-id="10c99-213">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="10c99-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Ansicht "Weiterleitungen" im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="10c99-215">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="10c99-216">Detailtabellenansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="10c99-217">Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="10c99-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="10c99-218">**Weiterleitungen:** Der Wert **"Transportregel"** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="10c99-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="10c99-219">**Weiterleitungstyp:** Der Wert **Postfachregel** oder **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="10c99-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="10c99-220">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="10c99-220">**Recipient name**</span></span>
- <span data-ttu-id="10c99-221">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="10c99-221">**Recipient domain**</span></span>
- <span data-ttu-id="10c99-222">**Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="10c99-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="10c99-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-223">**Count**</span></span>
- <span data-ttu-id="10c99-224">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="10c99-224">**First forward date**</span></span>

<span data-ttu-id="10c99-225">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="10c99-226">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="10c99-227">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-227">Mailflow status report</span></span>

<span data-ttu-id="10c99-228">Der **E-Mailflow-Statusbericht** ähnelt dem [Bericht "Gesendete und empfangene E-Mails"](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die am Edge zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="10c99-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="10c99-229">Dies ist der einzige Bericht, der Edgeschutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="10c99-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="10c99-230">Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="10c99-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="10c99-231">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Den E-Mail-Flussstatusbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="10c99-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="10c99-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenflussstatusberichts-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="10c99-234">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="10c99-235">Wenn Sie den Bericht  öffnen, ist standardmäßig die Registerkarte Typ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="10c99-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="10c99-236">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="10c99-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="10c99-237">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="10c99-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="10c99-238">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="10c99-238">**Direction**:</span></span>

  - <span data-ttu-id="10c99-239">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-239">**Inbound**</span></span>
  - <span data-ttu-id="10c99-240">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-240">**Outbound**</span></span>
  - <span data-ttu-id="10c99-241">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="10c99-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="10c99-242">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)</span><span class="sxs-lookup"><span data-stu-id="10c99-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="10c99-243">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="10c99-243">**Type**:</span></span>

  - <span data-ttu-id="10c99-244">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="10c99-244">**Good mail**</span></span>
  - <span data-ttu-id="10c99-245">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="10c99-245">**Malware**</span></span>
  - <span data-ttu-id="10c99-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="10c99-246">**Spam**</span></span>
  - <span data-ttu-id="10c99-247">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="10c99-247">**Edge protection**</span></span>
  - <span data-ttu-id="10c99-248">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="10c99-248">**Rule messages**</span></span>
  - <span data-ttu-id="10c99-249">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="10c99-249">**Phishing email**</span></span>

<span data-ttu-id="10c99-250">Das Diagramm ist nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="10c99-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="10c99-251">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="10c99-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="10c99-252">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="10c99-252">The data table contains the following information:</span></span>

- <span data-ttu-id="10c99-253">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="10c99-253">**Direction**</span></span>
- <span data-ttu-id="10c99-254">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10c99-254">**Type**</span></span>
- <span data-ttu-id="10c99-255">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="10c99-255">**24 hours**</span></span>
- <span data-ttu-id="10c99-256">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="10c99-256">**3 days**</span></span>
- <span data-ttu-id="10c99-257">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="10c99-257">**7 days**</span></span>
- <span data-ttu-id="10c99-258">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="10c99-258">**15 days**</span></span>
- <span data-ttu-id="10c99-259">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="10c99-259">**30 days**</span></span>

<span data-ttu-id="10c99-260">Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="10c99-261">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="10c99-262">**Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="10c99-263">**Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="10c99-264">**Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="10c99-265">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="10c99-265">**Export**:</span></span>

<span data-ttu-id="10c99-266">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="10c99-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="10c99-267">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="10c99-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="10c99-268">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="10c99-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="10c99-269">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="10c99-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="10c99-271">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="10c99-272">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="10c99-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="10c99-273">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="10c99-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="10c99-274">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="10c99-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="10c99-275">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="10c99-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="10c99-276">Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="10c99-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="10c99-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="10c99-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="10c99-278">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="10c99-278">**Export**:</span></span>

<span data-ttu-id="10c99-279">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="10c99-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="10c99-280">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="10c99-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="10c99-281">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="10c99-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="10c99-282">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="10c99-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="10c99-284">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="10c99-285">Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="10c99-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="10c99-286">Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="10c99-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="10c99-287">Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="10c99-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="10c99-288">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="10c99-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="10c99-289">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="10c99-289">**Direction**:</span></span>

  - <span data-ttu-id="10c99-290">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-290">**Inbound**</span></span>
  - <span data-ttu-id="10c99-291">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-291">**Outbound**</span></span>
  - <span data-ttu-id="10c99-292">**Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von Ein- und Ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="10c99-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="10c99-293">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="10c99-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="10c99-294">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="10c99-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="10c99-295">Dieses Diagramm zeigt die E-Mail-Anzahl nach:</span><span class="sxs-lookup"><span data-stu-id="10c99-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="10c99-296">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="10c99-296">**Total email**</span></span>
- <span data-ttu-id="10c99-297">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="10c99-297">**Email after edge protection**</span></span>
- <span data-ttu-id="10c99-298">**E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="10c99-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="10c99-299">**E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**</span><span class="sxs-lookup"><span data-stu-id="10c99-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="10c99-300">**E-Mails nach Antispam, Massenfilterung von E-Mails**</span><span class="sxs-lookup"><span data-stu-id="10c99-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="10c99-301">**E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="10c99-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="10c99-302">**E-Mail nach Datei- und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="10c99-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="10c99-303">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**</span><span class="sxs-lookup"><span data-stu-id="10c99-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="10c99-304"><sup>1</sup> Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="10c99-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="10c99-305">Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="10c99-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="10c99-306">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="10c99-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="10c99-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="10c99-307">**Date**</span></span>
- <span data-ttu-id="10c99-308">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="10c99-308">**Total email**</span></span>
- <span data-ttu-id="10c99-309">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="10c99-309">**Edge protection**</span></span>
- <span data-ttu-id="10c99-310">**Antischadsoftware, Dateireputation, Dateitypblock:**</span><span class="sxs-lookup"><span data-stu-id="10c99-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="10c99-311">**Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="10c99-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="10c99-312">**Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="10c99-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="10c99-313">**Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**</span><span class="sxs-lookup"><span data-stu-id="10c99-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="10c99-314">**URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="10c99-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="10c99-315">**Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.</span><span class="sxs-lookup"><span data-stu-id="10c99-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="10c99-316">**Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="10c99-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="10c99-317">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="10c99-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="10c99-318">**Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, Massen-E-Mails an die Empfänger zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="10c99-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="10c99-319">**Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="10c99-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="10c99-320">**Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="10c99-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="10c99-321">**Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="10c99-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="10c99-322">**Datei- und URL-Detonation (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="10c99-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="10c99-323">**Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.</span><span class="sxs-lookup"><span data-stu-id="10c99-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="10c99-324">**URL-Detonation:** Nachricht, gefiltert nach einer Safe Links-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="10c99-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="10c99-325">**Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** ZAP gibt die automatische Bereinigung zur Nullstunde an.</span><span class="sxs-lookup"><span data-stu-id="10c99-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="10c99-326">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10c99-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="10c99-327">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="10c99-327">**Export**:</span></span>

<span data-ttu-id="10c99-328">Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="10c99-329">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="10c99-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="10c99-330">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="10c99-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="10c99-331">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="10c99-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="10c99-332">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="10c99-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="10c99-333">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="10c99-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="10c99-334">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="10c99-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="10c99-336">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="10c99-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="10c99-337">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="10c99-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="10c99-338">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="10c99-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="10c99-339">Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="10c99-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="10c99-340">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="10c99-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="10c99-341">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="10c99-341">**Direction**:</span></span>

  - <span data-ttu-id="10c99-342">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-342">**Inbound**</span></span>
  - <span data-ttu-id="10c99-343">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="10c99-343">**Outbound**</span></span>
  - <span data-ttu-id="10c99-344">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="10c99-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="10c99-345">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)</span><span class="sxs-lookup"><span data-stu-id="10c99-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="10c99-346">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="10c99-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="10c99-347">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="10c99-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="10c99-348">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="10c99-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="10c99-349">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="10c99-349">**Total email**</span></span>
- <span data-ttu-id="10c99-350">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="10c99-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="10c99-351">**Keine Schadsoftware**, **Safe Erkennung von Anlagen,** <sup>\*</sup> Erkennung von **Antischadsoftwaremodulen** und **Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="10c99-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="10c99-352">**Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="10c99-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="10c99-353">**Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10c99-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="10c99-354">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="10c99-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="10c99-355">**Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="10c99-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="10c99-356"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="10c99-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="10c99-357">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="10c99-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="10c99-358">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="10c99-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="10c99-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="10c99-359">**Date**</span></span>
- <span data-ttu-id="10c99-360">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="10c99-360">**Total email**</span></span>
- <span data-ttu-id="10c99-361">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="10c99-361">**Edge filtered**</span></span>
- <span data-ttu-id="10c99-362">**Antischadsoftwaremodul, Safe Anlagen, Regel gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="10c99-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="10c99-363">**Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert werden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="10c99-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="10c99-364">**DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="10c99-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="10c99-365">**DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="10c99-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="10c99-366">**ERKENNUNG DER URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="10c99-366">**URL detonation detection**</span></span>
- <span data-ttu-id="10c99-367">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="10c99-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="10c99-368">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="10c99-368">**ZAP removed**</span></span>
- <span data-ttu-id="10c99-369">**Erkennung durch Safe Links**</span><span class="sxs-lookup"><span data-stu-id="10c99-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="10c99-370">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10c99-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="10c99-371">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="10c99-371">**Export**:</span></span>

<span data-ttu-id="10c99-372">Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="10c99-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="10c99-373">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="10c99-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="10c99-374">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="10c99-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="10c99-375">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="10c99-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="10c99-376">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="10c99-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="10c99-377">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="10c99-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="10c99-378">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="10c99-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="10c99-380">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="10c99-380">Sent and received email report</span></span>

<span data-ttu-id="10c99-381">Der Bericht **"Gesendete und empfangene E-Mails"** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails anzeigt, einschließlich Spamerkennungen, Schadsoftware und E-Mails, die als "gut" gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="10c99-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="10c99-382">Der Unterschied zwischen diesem Bericht und dem [E-Mailflow-Statusbericht](#mailflow-status-report) besteht darin, dass dieser Bericht keine Daten zu Nachrichten enthält, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu verstehen, dass eine Nachricht als eine Nachricht zählt, wenn sie an fünf Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="10c99-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="10c99-383">Die Aggregatansicht und die Detailansicht des Berichts ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="10c99-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="10c99-384">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Gesendete und empfangene E-Mails"** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="10c99-385">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="10c99-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="10c99-387">Berichtsansicht für den Bericht "Gesendete und empfangene E-Mails"</span><span class="sxs-lookup"><span data-stu-id="10c99-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="10c99-388">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10c99-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="10c99-389">**Unterteilen nach: Typ:** Das Diagramm zeigt alle verfügbaren Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="10c99-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="10c99-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="10c99-390">**Total**</span></span>
  - <span data-ttu-id="10c99-391">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="10c99-391">**Good mail**</span></span>
  - <span data-ttu-id="10c99-392">**Schadsoftware (Antischadsoftware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="10c99-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="10c99-393">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="10c99-393">**Spam detections**</span></span>
  - <span data-ttu-id="10c99-394">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="10c99-394">**Rule messages**</span></span>
  - <span data-ttu-id="10c99-395">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="10c99-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="10c99-396">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="10c99-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="10c99-398">**Aufschlüsselung nach: Richtung:** Das Diagramm zeigt Daten vom Typ **"Total",** **"Inbound"** und **"Outbound"** an.</span><span class="sxs-lookup"><span data-stu-id="10c99-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="10c99-399">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="10c99-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="10c99-401">**Drilldown nach** \> **Schadsoftware (Antischadsoftware):** Diese Auswahl führt Sie zum Bericht über [Schadsoftwareerkennungen.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="10c99-402">**Drilldown nach** \> **Spamerkennungen)**: Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="10c99-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="10c99-403">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="10c99-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="10c99-404">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="10c99-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="10c99-405">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="10c99-405">Direction values</span></span>
- <span data-ttu-id="10c99-406">Typwerte</span><span class="sxs-lookup"><span data-stu-id="10c99-406">Type values</span></span>

<span data-ttu-id="10c99-407">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="10c99-408">Detailtabellenansicht für den Bericht "Gesendete und empfangene E-Mails"</span><span class="sxs-lookup"><span data-stu-id="10c99-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="10c99-409">Wenn Sie in der Ansicht **Nach-Unten:Richtung** **auf** Detailtabelle anzeigen klicken, werden die folgenden Informationen angezeigt: </span><span class="sxs-lookup"><span data-stu-id="10c99-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="10c99-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="10c99-410">**Date (UTC)**</span></span>
- <span data-ttu-id="10c99-411">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10c99-411">**Type**</span></span>
- <span data-ttu-id="10c99-412">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="10c99-412">**Direction**</span></span>
- <span data-ttu-id="10c99-413">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="10c99-413">**Message count**</span></span>

<span data-ttu-id="10c99-414">Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="10c99-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="10c99-415">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="10c99-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="10c99-416">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="10c99-416">Direction values</span></span>
- <span data-ttu-id="10c99-417">Typwerte</span><span class="sxs-lookup"><span data-stu-id="10c99-417">Type values</span></span>

<span data-ttu-id="10c99-418">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="10c99-419">Bericht zu den wichtigsten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="10c99-419">Top senders and recipients report</span></span>

<span data-ttu-id="10c99-420">Der Bericht **"Häufigste Absender und Empfänger"** ist ein Kreisdiagramm, in dem Ihre wichtigsten E-Mail-Absender und -Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="10c99-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="10c99-421">Um den Bericht anzuzeigen, öffnen Sie das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie die wichtigsten Absender **und Empfänger** aus.</span><span class="sxs-lookup"><span data-stu-id="10c99-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="10c99-422">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="10c99-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget "Häufigste Absender und Empfänger" im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="10c99-424">Berichtsansicht für den Bericht "Häufigste Absender" und "Empfänger"</span><span class="sxs-lookup"><span data-stu-id="10c99-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="10c99-425">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10c99-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="10c99-426">**Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="10c99-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="10c99-427">**Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="10c99-428">**Anzeigen von Daten für \> die häufigsten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="10c99-429">**Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)</span><span class="sxs-lookup"><span data-stu-id="10c99-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="10c99-430">**Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="10c99-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="10c99-431">Die Zusammensetzung des Kreisdiagramms wird basierend auf diesen Auswahlen geändert.</span><span class="sxs-lookup"><span data-stu-id="10c99-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="10c99-432">Wenn Sie mit dem Mauszeiger auf einen Wedge im Kreisdiagramm zeigen, können Sie die Anzahl der gesendeten oder empfangenen Nachrichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="10c99-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="10c99-433">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in berichtsansicht im Bericht "Top senders and recipients"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="10c99-435">Detailtabellenansicht für den Bericht "Top senders" und "recipient"</span><span class="sxs-lookup"><span data-stu-id="10c99-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="10c99-436">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="10c99-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="10c99-437">**Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="10c99-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="10c99-438">**Die häufigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="10c99-438">**Top mail senders**</span></span>
  - <span data-ttu-id="10c99-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-439">**Count**</span></span>

- <span data-ttu-id="10c99-440">**Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="10c99-441">**Top-E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="10c99-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-442">**Count**</span></span>

- <span data-ttu-id="10c99-443">**Anzeigen von Daten für \> die häufigsten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="10c99-444">**Häufigste Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="10c99-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="10c99-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-445">**Count**</span></span>

- <span data-ttu-id="10c99-446">**Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)</span><span class="sxs-lookup"><span data-stu-id="10c99-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="10c99-447">**Die häufigsten Empfänger von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="10c99-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="10c99-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-448">**Count**</span></span>

- <span data-ttu-id="10c99-449">**Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="10c99-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="10c99-450">**Die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="10c99-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="10c99-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="10c99-451">**Count**</span></span>

<span data-ttu-id="10c99-452">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="10c99-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="10c99-453">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10c99-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="10c99-454">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="10c99-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="10c99-455">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="10c99-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="10c99-456">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="10c99-456">**Organization Management**</span></span>
- <span data-ttu-id="10c99-457">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="10c99-457">**Security Administrator**</span></span>
- <span data-ttu-id="10c99-458">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="10c99-458">**Security Reader**</span></span>
- <span data-ttu-id="10c99-459">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="10c99-459">**Global Reader**</span></span>

<span data-ttu-id="10c99-460">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="10c99-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="10c99-461">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10c99-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="10c99-462">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="10c99-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="10c99-463">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="10c99-463">Related topics</span></span>

[<span data-ttu-id="10c99-464">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="10c99-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="10c99-465">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="10c99-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="10c99-466">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="10c99-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="10c99-467">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="10c99-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
