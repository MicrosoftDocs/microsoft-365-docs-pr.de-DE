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
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029481"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="bfae6-103">Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bfae6-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bfae6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="bfae6-104">**Applies to**</span></span>
- [<span data-ttu-id="bfae6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bfae6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bfae6-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="bfae6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bfae6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfae6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="bfae6-108">Die meisten der in diesem Thema beschriebenen Berichte sind im Exchange Admin Center (EAC) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bfae6-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="bfae6-109">Weitere Informationen finden Sie [unter Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="bfae6-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="bfae6-110">Der [Exchange-Transportregelbericht](view-email-security-reports.md#exchange-transport-rule-report) ist im Microsoft 365 Defender-Portal verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bfae6-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="bfae6-111">Zusätzlich zu den Nachrichtenflussberichten, die im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im Security & Compliance Center verfügbar sind, stehen im Berichtsdashboard eine Vielzahl zusätzlicher Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="bfae6-112">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & [Compliance Center](https://protection.office.com) anzeigen, indem Sie zum **Berichtsdashboard** \> wechseln.</span><span class="sxs-lookup"><span data-stu-id="bfae6-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="bfae6-113">Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="bfae6-115">Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-115">Connector report</span></span>

<span data-ttu-id="bfae6-116">Der **Connectorbericht** zeigt Nachrichtenflussaktivitäten auf den [eingehenden und ausgehenden Connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="bfae6-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="bfae6-117">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Connectorbericht"** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="bfae6-118">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorberichts-Widget im Berichtsdashboard](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="bfae6-120">Berichtsansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-120">Report view for the Connector report</span></span>

<span data-ttu-id="bfae6-121">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bfae6-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="bfae6-122">**Anzeigen von Daten nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten an, nach:</span><span class="sxs-lookup"><span data-stu-id="bfae6-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="bfae6-123">**Total**</span><span class="sxs-lookup"><span data-stu-id="bfae6-123">**Total**</span></span>
  - <span data-ttu-id="bfae6-124">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="bfae6-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="bfae6-125">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="bfae6-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="bfae6-126">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="bfae6-127">Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine dieser Optionen oder **den gesamten Nachrichtenfluss** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Anzeigen von Daten nach E-Mail-Fluss im Connector-Bericht](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="bfae6-129">**Anzeigen von Daten nach: TLS-Verwendung:** Dieses Diagramm zeigt den Prozentsatz der TLS-Versionsnutzung (Transport Layer Security) für den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="bfae6-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="bfae6-130">Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine der folgenden Optionen auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="bfae6-131">**Alle Nachrichtenübermittlungen**</span><span class="sxs-lookup"><span data-stu-id="bfae6-131">**All mail flow**</span></span>
  - <span data-ttu-id="bfae6-132">**Aus dem Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="bfae6-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="bfae6-133">**Ins Internet ohne Connector**</span><span class="sxs-lookup"><span data-stu-id="bfae6-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="bfae6-134">Ein bestimmter Connector, den Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-134">A specific connector that you've configured.</span></span>

  ![Anzeigen von Daten nach TLS-Verwendung im Connector-Bericht](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="bfae6-136">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="bfae6-137">Detailtabellenansicht für den Connectorbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-137">Details table view for the Connector report</span></span>

<span data-ttu-id="bfae6-138">Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bfae6-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="bfae6-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="bfae6-139">**Date**</span></span>
- <span data-ttu-id="bfae6-140">**Verbindungsrichtung und -name**</span><span class="sxs-lookup"><span data-stu-id="bfae6-140">**Connector direction and name**</span></span>
- <span data-ttu-id="bfae6-141">**Connectortyp**</span><span class="sxs-lookup"><span data-stu-id="bfae6-141">**Connector type**</span></span>
- <span data-ttu-id="bfae6-142">**Tls erzwungen?**: Der Wert **True** oder **False**.</span><span class="sxs-lookup"><span data-stu-id="bfae6-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="bfae6-143">**Kein TLS** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="bfae6-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="bfae6-144">**TLS 1.0** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="bfae6-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="bfae6-145">**TLS 1.1** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="bfae6-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="bfae6-146">**TLS 1.2** (Prozentsatz)</span><span class="sxs-lookup"><span data-stu-id="bfae6-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="bfae6-147">**Volume:** Die Anzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="bfae6-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="bfae6-148">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bfae6-149">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="bfae6-150">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-150">Exchange transport rule report</span></span>

<span data-ttu-id="bfae6-151">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bfae6-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="bfae6-152">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Exchange-Transportregel** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="bfae6-153">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget im Berichtsdashboard](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="bfae6-155">Berichtsansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="bfae6-156">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bfae6-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="bfae6-157">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="bfae6-158">**Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Schweregrad:** Dieses Diagramm zeigt die Anzahl der Meldungen mit **hohem und** **mittlerem Schweregrad** sowie Meldungen mit **dem niedrigen Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="bfae6-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="bfae6-159">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="bfae6-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="bfae6-160">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="bfae6-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="bfae6-161">**Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="bfae6-162">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="bfae6-163">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="bfae6-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="bfae6-164">**Anzeigen von Daten für: Kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="bfae6-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="bfae6-165">**Show data for: Low volume of content detected U.S. Mof Act**</span><span class="sxs-lookup"><span data-stu-id="bfae6-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="bfae6-166">**Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Diese Ansicht zeigt die Anzahl der Nachrichten mit **hohem und** **mittlerem Schweregrad** sowie Nachrichten mit **dem niedrigen Schweregrad,** die von DLP-Transportregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="bfae6-167">Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="bfae6-168">**Anzeigen von Daten für: Alle DLP-Transportregeln**</span><span class="sxs-lookup"><span data-stu-id="bfae6-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="bfae6-169">**Anzeigen von Daten für: Kompromittierte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="bfae6-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="bfae6-170">**Show data for: Low volume of content detected U.S. Mof Act**</span><span class="sxs-lookup"><span data-stu-id="bfae6-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="bfae6-171">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="bfae6-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="bfae6-172">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="bfae6-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="bfae6-173">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-173">Direction values</span></span>
- <span data-ttu-id="bfae6-174">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-174">Severity values</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="bfae6-176">Detailtabellenansicht für den Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="bfae6-177">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bfae6-178">**Anzeigen von Daten nach: Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="bfae6-179">**Date**</span><span class="sxs-lookup"><span data-stu-id="bfae6-179">**Date**</span></span>
  - <span data-ttu-id="bfae6-180">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="bfae6-180">**Transport rule**</span></span>
  - <span data-ttu-id="bfae6-181">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="bfae6-181">**Subject**</span></span>
  - <span data-ttu-id="bfae6-182">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="bfae6-182">**Sender address**</span></span>
  - <span data-ttu-id="bfae6-183">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="bfae6-183">**Recipient address**</span></span>
  - <span data-ttu-id="bfae6-184">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="bfae6-184">**Severity**</span></span>
  - <span data-ttu-id="bfae6-185">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-185">**Direction**</span></span>

- <span data-ttu-id="bfae6-186">**Anzeigen von Daten nach: DLP Exchange-Transportregeln:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="bfae6-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="bfae6-187">**Date**</span></span>
  - <span data-ttu-id="bfae6-188">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="bfae6-188">**DLP policy**</span></span>
  - <span data-ttu-id="bfae6-189">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="bfae6-189">**Transport rule**</span></span>
  - <span data-ttu-id="bfae6-190">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="bfae6-190">**Subject**</span></span>
  - <span data-ttu-id="bfae6-191">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="bfae6-191">**Sender address**</span></span>
  - <span data-ttu-id="bfae6-192">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="bfae6-192">**Recipient address**</span></span>
  - <span data-ttu-id="bfae6-193">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="bfae6-193">**Severity**</span></span>
  - <span data-ttu-id="bfae6-194">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-194">**Direction**</span></span>

<span data-ttu-id="bfae6-195">Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="bfae6-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="bfae6-196">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="bfae6-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="bfae6-197">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-197">Direction values</span></span>
- <span data-ttu-id="bfae6-198">Schweregradwerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-198">Severity values</span></span>

<span data-ttu-id="bfae6-199">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="bfae6-200">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-200">Forwarding report</span></span>

<span data-ttu-id="bfae6-201">Der **Weiterleitungsbericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation von Exchange Online Postfächern an externe Domänen an.</span><span class="sxs-lookup"><span data-stu-id="bfae6-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="bfae6-202">Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein kompromittiertes Konto hinweisen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="bfae6-203">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Weiterleitungsbericht"** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="bfae6-204">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Weiterleitung des Berichts-Widgets im Berichtsdashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="bfae6-206">Berichtsansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="bfae6-207">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bfae6-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bfae6-208">**Anzeigen von Daten für: Weiterleitungsmethoden:** Die folgenden Methoden werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bfae6-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="bfae6-209">**Transportregel**: Wird auch als [Nachrichtenflussregeln bezeichnet.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="bfae6-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="bfae6-210">**Postfachregel**: Wird auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="bfae6-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="bfae6-212">**Anzeigen von Daten für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.</span><span class="sxs-lookup"><span data-stu-id="bfae6-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Ansicht "Weiterleitungsdomänen" im Bericht "Weiterleitung"](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="bfae6-214">**Show data for: forwarders**: The following forwarders are shown:</span><span class="sxs-lookup"><span data-stu-id="bfae6-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="bfae6-215">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="bfae6-215">**Transport rule**</span></span>
  - <span data-ttu-id="bfae6-216">Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="bfae6-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Ansicht "Weiterleitungen" im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="bfae6-218">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="bfae6-219">Detailtabellenansicht für den Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="bfae6-220">Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bfae6-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="bfae6-221">**Weiterleitungen:** Der Wert **"Transportregel"** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.</span><span class="sxs-lookup"><span data-stu-id="bfae6-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="bfae6-222">**Weiterleitungstyp:** Der Wert **Postfachregel** oder **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="bfae6-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="bfae6-223">**Empfängername**</span><span class="sxs-lookup"><span data-stu-id="bfae6-223">**Recipient name**</span></span>
- <span data-ttu-id="bfae6-224">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="bfae6-224">**Recipient domain**</span></span>
- <span data-ttu-id="bfae6-225">**Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="bfae6-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="bfae6-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-226">**Count**</span></span>
- <span data-ttu-id="bfae6-227">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="bfae6-227">**First forward date**</span></span>

<span data-ttu-id="bfae6-228">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bfae6-229">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="bfae6-230">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-230">Mailflow status report</span></span>

<span data-ttu-id="bfae6-231">Der **E-Mailflow-Statusbericht** ähnelt dem [Bericht "Gesendete und empfangene E-Mails"](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die am Edge zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="bfae6-232">Dies ist der einzige Bericht, der Edge-Schutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="bfae6-233">Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="bfae6-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="bfae6-234">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Den E-Mail-Flussstatusbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="bfae6-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Nachrichtenflussstatusberichts-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="bfae6-237">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="bfae6-238">Wenn Sie den Bericht  öffnen, ist standardmäßig die Registerkarte Typ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="bfae6-239">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="bfae6-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="bfae6-240">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="bfae6-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="bfae6-241">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-241">**Direction**:</span></span>

  - <span data-ttu-id="bfae6-242">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-242">**Inbound**</span></span>
  - <span data-ttu-id="bfae6-243">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-243">**Outbound**</span></span>
  - <span data-ttu-id="bfae6-244">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="bfae6-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="bfae6-245">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)</span><span class="sxs-lookup"><span data-stu-id="bfae6-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="bfae6-246">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-246">**Type**:</span></span>

  - <span data-ttu-id="bfae6-247">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="bfae6-247">**Good mail**</span></span>
  - <span data-ttu-id="bfae6-248">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="bfae6-248">**Malware**</span></span>
  - <span data-ttu-id="bfae6-249">**Spam**</span><span class="sxs-lookup"><span data-stu-id="bfae6-249">**Spam**</span></span>
  - <span data-ttu-id="bfae6-250">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="bfae6-250">**Edge protection**</span></span>
  - <span data-ttu-id="bfae6-251">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="bfae6-251">**Rule messages**</span></span>
  - <span data-ttu-id="bfae6-252">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="bfae6-252">**Phishing email**</span></span>

<span data-ttu-id="bfae6-253">Das Diagramm ist nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="bfae6-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="bfae6-254">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="bfae6-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="bfae6-255">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-255">The data table contains the following information:</span></span>

- <span data-ttu-id="bfae6-256">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-256">**Direction**</span></span>
- <span data-ttu-id="bfae6-257">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bfae6-257">**Type**</span></span>
- <span data-ttu-id="bfae6-258">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="bfae6-258">**24 hours**</span></span>
- <span data-ttu-id="bfae6-259">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="bfae6-259">**3 days**</span></span>
- <span data-ttu-id="bfae6-260">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="bfae6-260">**7 days**</span></span>
- <span data-ttu-id="bfae6-261">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="bfae6-261">**15 days**</span></span>
- <span data-ttu-id="bfae6-262">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="bfae6-262">**30 days**</span></span>

<span data-ttu-id="bfae6-263">Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="bfae6-264">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="bfae6-265">**Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="bfae6-266">**Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="bfae6-267">**Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="bfae6-268">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="bfae6-268">**Export**:</span></span>

<span data-ttu-id="bfae6-269">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="bfae6-270">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="bfae6-271">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="bfae6-272">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="bfae6-274">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="bfae6-275">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfae6-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="bfae6-276">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="bfae6-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="bfae6-277">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="bfae6-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="bfae6-278">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfae6-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="bfae6-279">Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="bfae6-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="bfae6-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="bfae6-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="bfae6-281">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="bfae6-281">**Export**:</span></span>

<span data-ttu-id="bfae6-282">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="bfae6-283">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="bfae6-284">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="bfae6-285">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="bfae6-287">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="bfae6-288">Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="bfae6-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="bfae6-289">Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="bfae6-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="bfae6-290">Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="bfae6-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="bfae6-291">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="bfae6-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="bfae6-292">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-292">**Direction**:</span></span>

  - <span data-ttu-id="bfae6-293">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-293">**Inbound**</span></span>
  - <span data-ttu-id="bfae6-294">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-294">**Outbound**</span></span>
  - <span data-ttu-id="bfae6-295">**Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. Absender abc@domain.com sendet an Empfänger xyz@domain.com (separat von Ein- und Ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="bfae6-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="bfae6-296">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="bfae6-297">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="bfae6-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="bfae6-298">Dieses Diagramm zeigt die E-Mail-Anzahl nach:</span><span class="sxs-lookup"><span data-stu-id="bfae6-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="bfae6-299">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="bfae6-299">**Total email**</span></span>
- <span data-ttu-id="bfae6-300">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="bfae6-300">**Email after edge protection**</span></span>
- <span data-ttu-id="bfae6-301">**E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="bfae6-302">**E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**</span><span class="sxs-lookup"><span data-stu-id="bfae6-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="bfae6-303">**E-Mails nach Antispam, Massenfilterung von E-Mails**</span><span class="sxs-lookup"><span data-stu-id="bfae6-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="bfae6-304">**E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bfae6-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="bfae6-305">**E-Mail nach Datei- und URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bfae6-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="bfae6-306">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="bfae6-307"><sup>1</sup> Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="bfae6-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="bfae6-308">Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="bfae6-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="bfae6-309">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="bfae6-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="bfae6-310">**Date**</span><span class="sxs-lookup"><span data-stu-id="bfae6-310">**Date**</span></span>
- <span data-ttu-id="bfae6-311">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="bfae6-311">**Total email**</span></span>
- <span data-ttu-id="bfae6-312">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="bfae6-312">**Edge protection**</span></span>
- <span data-ttu-id="bfae6-313">**Antischadsoftware, Dateireputation, Dateitypblock:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="bfae6-314">**Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="bfae6-315">**Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="bfae6-316">**Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="bfae6-317">**URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="bfae6-318">**Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bfae6-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="bfae6-319">**Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="bfae6-320">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="bfae6-321">**Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, Massen-E-Mails an die Empfänger zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="bfae6-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="bfae6-322">**Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="bfae6-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="bfae6-323">**Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bfae6-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="bfae6-324">**Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bfae6-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="bfae6-325">**Datei- und URL-Detonation (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="bfae6-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="bfae6-326">**Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.</span><span class="sxs-lookup"><span data-stu-id="bfae6-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="bfae6-327">**URL-Detonation:** Nachricht, gefiltert nach einer Safe-Verknüpfungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="bfae6-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="bfae6-328">**Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** ZAP gibt die automatische Bereinigung zur Nullstunde an.</span><span class="sxs-lookup"><span data-stu-id="bfae6-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="bfae6-329">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="bfae6-330">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="bfae6-330">**Export**:</span></span>

<span data-ttu-id="bfae6-331">Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="bfae6-332">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="bfae6-333">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="bfae6-334">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="bfae6-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="bfae6-335">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="bfae6-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="bfae6-336">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="bfae6-337">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="bfae6-339">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="bfae6-340">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="bfae6-341">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="bfae6-342">Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="bfae6-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="bfae6-343">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="bfae6-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="bfae6-344">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-344">**Direction**:</span></span>

  - <span data-ttu-id="bfae6-345">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-345">**Inbound**</span></span>
  - <span data-ttu-id="bfae6-346">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="bfae6-346">**Outbound**</span></span>
  - <span data-ttu-id="bfae6-347">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="bfae6-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="bfae6-348">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)</span><span class="sxs-lookup"><span data-stu-id="bfae6-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="bfae6-349">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="bfae6-350">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="bfae6-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="bfae6-351">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="bfae6-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="bfae6-352">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="bfae6-352">**Total email**</span></span>
- <span data-ttu-id="bfae6-353">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="bfae6-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="bfae6-354">**Keine Schadsoftware**, **Safe Erkennung von Anlagen,** <sup>\*</sup> Erkennung von **Antischadsoftwaremodulen** und **Regelmeldungen**</span><span class="sxs-lookup"><span data-stu-id="bfae6-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="bfae6-355">**Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="bfae6-356">**Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bfae6-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="bfae6-357">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="bfae6-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="bfae6-358">**Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="bfae6-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="bfae6-359"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="bfae6-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="bfae6-360">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="bfae6-361">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="bfae6-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="bfae6-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="bfae6-362">**Date**</span></span>
- <span data-ttu-id="bfae6-363">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="bfae6-363">**Total email**</span></span>
- <span data-ttu-id="bfae6-364">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="bfae6-364">**Edge filtered**</span></span>
- <span data-ttu-id="bfae6-365">**Antischadsoftwaremodul, Safe Anlagen, Regel gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="bfae6-366">**Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert werden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="bfae6-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="bfae6-367">**DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="bfae6-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="bfae6-368">**DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="bfae6-369">**ERKENNUNG DER URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="bfae6-369">**URL detonation detection**</span></span>
- <span data-ttu-id="bfae6-370">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="bfae6-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="bfae6-371">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="bfae6-371">**ZAP removed**</span></span>
- <span data-ttu-id="bfae6-372">**Erkennung durch Safe Links**</span><span class="sxs-lookup"><span data-stu-id="bfae6-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="bfae6-373">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="bfae6-374">**Exportieren**:</span><span class="sxs-lookup"><span data-stu-id="bfae6-374">**Export**:</span></span>

<span data-ttu-id="bfae6-375">Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="bfae6-376">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="bfae6-377">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="bfae6-378">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="bfae6-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="bfae6-379">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="bfae6-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="bfae6-380">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="bfae6-381">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfae6-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="bfae6-383">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="bfae6-383">Sent and received email report</span></span>

<span data-ttu-id="bfae6-384">Der Bericht **"Gesendete und empfangene E-Mails"** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails anzeigt, einschließlich Spamerkennungen, Schadsoftware und E-Mails, die als "gut" gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="bfae6-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="bfae6-385">Der Unterschied zwischen diesem Bericht und dem [E-Mailflow-Statusbericht](#mailflow-status-report) besteht darin, dass dieser Bericht keine Daten zu Nachrichten enthält, die durch den Edgeschutz blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="bfae6-386">**Hinweis:** Es ist wichtig zu verstehen, dass eine Nachricht als eine Nachricht zählt, wenn sie an fünf Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfae6-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="bfae6-387">Die Aggregatansicht und die Detailansicht des Berichts ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="bfae6-388">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Gesendete und empfangene E-Mails"** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="bfae6-389">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="bfae6-391">Berichtsansicht für den Bericht "Gesendete und empfangene E-Mails"</span><span class="sxs-lookup"><span data-stu-id="bfae6-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="bfae6-392">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bfae6-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bfae6-393">**Unterteilen nach: Typ:** Das Diagramm zeigt alle verfügbaren Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="bfae6-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="bfae6-394">**Total**</span><span class="sxs-lookup"><span data-stu-id="bfae6-394">**Total**</span></span>
  - <span data-ttu-id="bfae6-395">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="bfae6-395">**Good mail**</span></span>
  - <span data-ttu-id="bfae6-396">**Schadsoftware (Antischadsoftware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="bfae6-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="bfae6-397">**Spamerkennungen**</span><span class="sxs-lookup"><span data-stu-id="bfae6-397">**Spam detections**</span></span>
  - <span data-ttu-id="bfae6-398">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="bfae6-398">**Rule messages**</span></span>
  - <span data-ttu-id="bfae6-399">**Erweiterte Schadsoftware** (Microsoft Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="bfae6-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="bfae6-400">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="bfae6-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="bfae6-402">**Aufschlüsselung nach: Richtung:** Das Diagramm zeigt Daten vom Typ **"Total",** **"Inbound"** und **"Outbound"** an.</span><span class="sxs-lookup"><span data-stu-id="bfae6-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="bfae6-403">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="bfae6-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="bfae6-405">**Drilldown nach** \> **Schadsoftware (Antischadsoftware):** Diese Auswahl führt Sie zum Bericht über [Schadsoftwareerkennungen.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="bfae6-406">**Drilldown nach** \> **Spamerkennungen)**: Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="bfae6-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="bfae6-407">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="bfae6-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="bfae6-408">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="bfae6-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="bfae6-409">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-409">Direction values</span></span>
- <span data-ttu-id="bfae6-410">Typwerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-410">Type values</span></span>

<span data-ttu-id="bfae6-411">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="bfae6-412">Detailtabellenansicht für den Bericht "Gesendete und empfangene E-Mails"</span><span class="sxs-lookup"><span data-stu-id="bfae6-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="bfae6-413">Wenn Sie in der Ansicht **Nach-Unten:Richtung** **auf** Detailtabelle anzeigen klicken, werden die folgenden Informationen angezeigt: </span><span class="sxs-lookup"><span data-stu-id="bfae6-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="bfae6-414">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-414">**Date (UTC)**</span></span>
- <span data-ttu-id="bfae6-415">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bfae6-415">**Type**</span></span>
- <span data-ttu-id="bfae6-416">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-416">**Direction**</span></span>
- <span data-ttu-id="bfae6-417">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="bfae6-417">**Message count**</span></span>

<span data-ttu-id="bfae6-418">Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="bfae6-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="bfae6-419">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="bfae6-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="bfae6-420">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-420">Direction values</span></span>
- <span data-ttu-id="bfae6-421">Typwerte</span><span class="sxs-lookup"><span data-stu-id="bfae6-421">Type values</span></span>

<span data-ttu-id="bfae6-422">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="bfae6-423">Bericht zu den wichtigsten Absendern und Empfängern</span><span class="sxs-lookup"><span data-stu-id="bfae6-423">Top senders and recipients report</span></span>

<span data-ttu-id="bfae6-424">Der Bericht **"Häufigste Absender und Empfänger"** ist ein Kreisdiagramm, in dem Ihre wichtigsten E-Mail-Absender und -Empfänger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bfae6-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="bfae6-425">Um den Bericht anzuzeigen, öffnen Sie das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie die wichtigsten Absender **und Empfänger** aus.</span><span class="sxs-lookup"><span data-stu-id="bfae6-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="bfae6-426">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="bfae6-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget "Häufigste Absender und Empfänger" im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="bfae6-428">Berichtsansicht für den Bericht "Häufigste Absender" und "Empfänger"</span><span class="sxs-lookup"><span data-stu-id="bfae6-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="bfae6-429">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bfae6-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bfae6-430">**Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="bfae6-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="bfae6-431">**Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="bfae6-432">**Anzeigen von Daten für \> die häufigsten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="bfae6-433">**Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)</span><span class="sxs-lookup"><span data-stu-id="bfae6-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="bfae6-434">**Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="bfae6-435">Die Zusammensetzung des Kreisdiagramms wird basierend auf diesen Auswahlen geändert.</span><span class="sxs-lookup"><span data-stu-id="bfae6-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="bfae6-436">Wenn Sie mit dem Mauszeiger auf einen Wedge im Kreisdiagramm zeigen, können Sie die Anzahl der gesendeten oder empfangenen Nachrichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bfae6-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="bfae6-437">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Kreisdiagramm in berichtsansicht im Bericht "Top senders and recipients"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="bfae6-439">Detailtabellenansicht für den Bericht "Top senders" und "recipient"</span><span class="sxs-lookup"><span data-stu-id="bfae6-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="bfae6-440">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="bfae6-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bfae6-441">**Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="bfae6-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="bfae6-442">**Die häufigsten E-Mail-Absender**</span><span class="sxs-lookup"><span data-stu-id="bfae6-442">**Top mail senders**</span></span>
  - <span data-ttu-id="bfae6-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-443">**Count**</span></span>

- <span data-ttu-id="bfae6-444">**Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="bfae6-445">**Top-E-Mail-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="bfae6-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-446">**Count**</span></span>

- <span data-ttu-id="bfae6-447">**Anzeigen von Daten für \> die häufigsten Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="bfae6-448">**Häufigste Spamempfänger**</span><span class="sxs-lookup"><span data-stu-id="bfae6-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="bfae6-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-449">**Count**</span></span>

- <span data-ttu-id="bfae6-450">**Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)</span><span class="sxs-lookup"><span data-stu-id="bfae6-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="bfae6-451">**Die häufigsten Empfänger von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="bfae6-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="bfae6-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-452">**Count**</span></span>

- <span data-ttu-id="bfae6-453">**Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="bfae6-454">**Die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**</span><span class="sxs-lookup"><span data-stu-id="bfae6-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="bfae6-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="bfae6-455">**Count**</span></span>

<span data-ttu-id="bfae6-456">Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="bfae6-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bfae6-457">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="bfae6-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="bfae6-458">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="bfae6-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="bfae6-459">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="bfae6-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="bfae6-460">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="bfae6-460">**Organization Management**</span></span>
- <span data-ttu-id="bfae6-461">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="bfae6-461">**Security Administrator**</span></span>
- <span data-ttu-id="bfae6-462">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="bfae6-462">**Security Reader**</span></span>
- <span data-ttu-id="bfae6-463">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="bfae6-463">**Global Reader**</span></span>

<span data-ttu-id="bfae6-464">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bfae6-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bfae6-465">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bfae6-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bfae6-466">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bfae6-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bfae6-467">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bfae6-467">Related topics</span></span>

[<span data-ttu-id="bfae6-468">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bfae6-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="bfae6-469">Nachrichtenübermittlung und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bfae6-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="bfae6-470">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bfae6-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="bfae6-471">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="bfae6-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
