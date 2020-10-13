---
title: Anzeigen von Berichten für Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Suchen und Verwenden von Berichten für Office 365 Advanced Threat Protection im Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2bb4b0248294589b3e6e7a1a095e4f63d47d8e2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446299"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="7102d-103">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7102d-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7102d-104">Office 365 Advanced Threat Protection (ATP)-Organisationen (beispielsweise Microsoft 365 E5-Abonnements oder ATP Plan 1 oder ATP Plan 2-Add-ons) enthalten eine Vielzahl von sicherheitsbezogenen Berichten.</span><span class="sxs-lookup"><span data-stu-id="7102d-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="7102d-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-atp-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard**Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="7102d-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="7102d-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="7102d-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Das Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="7102d-108">Advanced Threat Protection-Bericht zu Dateitypen</span><span class="sxs-lookup"><span data-stu-id="7102d-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="7102d-109">Der Bericht über **Erweiterte Bedrohungsschutz-Dateitypen** zeigt Ihnen den Typ der Dateien an, die von [sicheren Anlagen](atp-safe-attachments.md)als schädlich erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="7102d-110">Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während in der Detailansicht nur 10 Tage Filterung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="7102d-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="7102d-111">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** \> - **Dashboard** , und wählen Sie **Office ATP-Dateitypen**aus.</span><span class="sxs-lookup"><span data-stu-id="7102d-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="7102d-112">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="7102d-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Office ATP-Dateitypen-Widget im Dashboard "Berichte"](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="7102d-114">Die Informationen in diesem Bericht sind auch im [Nachrichten Disposition-Bericht für erweiterte Bedrohungen](#advanced-threat-protection-message-disposition-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7102d-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="7102d-115">Berichtsansicht für den Bericht "Erweiterte Bedrohungsschutz-Dateitypen"</span><span class="sxs-lookup"><span data-stu-id="7102d-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="7102d-116">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7102d-116">The following views are available:</span></span>

- <span data-ttu-id="7102d-117">**Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7102d-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="7102d-118">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="7102d-119">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="7102d-120">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="7102d-121">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="7102d-122">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="7102d-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="7102d-123">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="7102d-124">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="7102d-125">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="7102d-125">**Others**</span></span>

  <span data-ttu-id="7102d-126">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="7102d-128">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-129">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-130">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="7102d-131">**Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7102d-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="7102d-132">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="7102d-132">**Block access**</span></span>
  - <span data-ttu-id="7102d-133">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="7102d-133">**Messages replaced**</span></span>
  - <span data-ttu-id="7102d-134">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="7102d-134">**Messages monitored**</span></span>
  - <span data-ttu-id="7102d-135">**Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="7102d-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="7102d-137">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-138">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-139">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="7102d-140">Detailtabellen Ansicht für den Bericht "Erweiterte Bedrohungsschutz-Dateitypen"</span><span class="sxs-lookup"><span data-stu-id="7102d-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="7102d-141">Wenn Sie auf **Detailtabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="7102d-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="7102d-142">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="7102d-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7102d-143">**Daten nach: File anzeigen**:</span><span class="sxs-lookup"><span data-stu-id="7102d-143">**View data by: File**:</span></span>

  - <span data-ttu-id="7102d-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="7102d-144">**Date**</span></span>
  - <span data-ttu-id="7102d-145">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-145">**Recipient address**</span></span>
  - <span data-ttu-id="7102d-146">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-146">**Sender address**</span></span>
  - <span data-ttu-id="7102d-147">**Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7102d-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="7102d-148">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="7102d-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="7102d-149">**Datei**</span><span class="sxs-lookup"><span data-stu-id="7102d-149">**File**</span></span>

  <span data-ttu-id="7102d-150">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-151">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-152">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="7102d-153">**Anzeigen von Daten nach: Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="7102d-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="7102d-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="7102d-154">**Date**</span></span>
  - <span data-ttu-id="7102d-155">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-155">**Recipient address**</span></span>
  - <span data-ttu-id="7102d-156">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-156">**Sender address**</span></span>
  - <span data-ttu-id="7102d-157">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="7102d-157">**Message ID**</span></span>
  - <span data-ttu-id="7102d-158">**Datei**</span><span class="sxs-lookup"><span data-stu-id="7102d-158">**File**</span></span>
  - <span data-ttu-id="7102d-159">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="7102d-159">**Subject**</span></span>

  <span data-ttu-id="7102d-160">Wenn Sie auf **Filter**klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="7102d-161">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-162">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="7102d-163">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="7102d-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="7102d-164">Advanced Threat Protection-Bericht zum Nachrichtenstatus</span><span class="sxs-lookup"><span data-stu-id="7102d-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="7102d-165">Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="7102d-166">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Office ATP-Nachrichten Disposition**aus.</span><span class="sxs-lookup"><span data-stu-id="7102d-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="7102d-167">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="7102d-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Office 365 Widget "ATP-Nachrichten Disposition" im Dashboard "Berichte"](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="7102d-169">Die Informationen in diesem Bericht sind auch im [Bericht erweiterte Bedrohungsschutz-Dateitypen](#advanced-threat-protection-file-types-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7102d-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="7102d-170">Berichtsansicht für den Nachrichten Disposition-Bericht "Advanced Threat Protection"</span><span class="sxs-lookup"><span data-stu-id="7102d-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="7102d-171">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7102d-171">The following views are available:</span></span>

- <span data-ttu-id="7102d-172">**Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7102d-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="7102d-173">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="7102d-173">**Block access**</span></span>
  - <span data-ttu-id="7102d-174">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="7102d-174">**Messages replaced**</span></span>
  - <span data-ttu-id="7102d-175">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="7102d-175">**Messages monitored**</span></span>
  - <span data-ttu-id="7102d-176">**Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="7102d-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="7102d-178">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-179">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-180">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="7102d-181">**Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7102d-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="7102d-182">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="7102d-183">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="7102d-184">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="7102d-185">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="7102d-186">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="7102d-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="7102d-187">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="7102d-188">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="7102d-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="7102d-189">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="7102d-189">**Others**</span></span>

  <span data-ttu-id="7102d-190">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="7102d-192">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-193">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-194">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="7102d-195">Ansicht "Detailtabelle" für den Bericht "Erweiterte Bedrohungsschutz Nachrichten Disposition"</span><span class="sxs-lookup"><span data-stu-id="7102d-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="7102d-196">Wenn Sie auf **Detailtabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="7102d-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="7102d-197">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="7102d-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7102d-198">**Anzeigen von Daten nach: Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="7102d-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="7102d-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="7102d-199">**Date**</span></span>
  - <span data-ttu-id="7102d-200">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-200">**Recipient address**</span></span>
  - <span data-ttu-id="7102d-201">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-201">**Sender address**</span></span>
  - <span data-ttu-id="7102d-202">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="7102d-202">**Message ID**</span></span>
  - <span data-ttu-id="7102d-203">**Datei**</span><span class="sxs-lookup"><span data-stu-id="7102d-203">**File**</span></span>
  - <span data-ttu-id="7102d-204">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="7102d-204">**Subject**</span></span>

  <span data-ttu-id="7102d-205">Wenn Sie auf **Filter**klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="7102d-206">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-207">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="7102d-208">**Daten nach: File anzeigen**:</span><span class="sxs-lookup"><span data-stu-id="7102d-208">**View data by: File**:</span></span>

  - <span data-ttu-id="7102d-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="7102d-209">**Date**</span></span>
  - <span data-ttu-id="7102d-210">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-210">**Recipient address**</span></span>
  - <span data-ttu-id="7102d-211">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="7102d-211">**Sender address**</span></span>
  - <span data-ttu-id="7102d-212">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="7102d-212">**Message ID**</span></span>
  - <span data-ttu-id="7102d-213">**Datei**</span><span class="sxs-lookup"><span data-stu-id="7102d-213">**File**</span></span>

  <span data-ttu-id="7102d-214">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-215">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-216">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="7102d-217">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="7102d-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="7102d-218">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="7102d-218">Threat protection status report</span></span>

<span data-ttu-id="7102d-219">Der **Statusbericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails zusammengefasst werden, die durch [Exchange Online Schutz](exchange-online-protection-overview.md) (EoP) und Office 365 ATP erkannt und blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7102d-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="7102d-220">Weitere Informationen finden Sie unter [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="7102d-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="7102d-221">URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="7102d-221">URL threat protection report</span></span>

<span data-ttu-id="7102d-222">Der **Bericht über den URL-Bedrohungsschutz** bietet zusammenfassende und Trend Ansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen von [sicheren Links](atp-safe-links.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7102d-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="7102d-223">In diesem Bericht werden keine klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links angewendet die Option **Benutzerklicks nicht nachverfolgen** aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="7102d-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="7102d-224">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **URL-Schutzbericht**aus.</span><span class="sxs-lookup"><span data-stu-id="7102d-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="7102d-225">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="7102d-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget "URL Protection-Bericht" im Dashboard "Berichte"](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="7102d-227">Hierbei handelt es sich um einen *Schutz Trendbericht*, was bedeutet, dass Datentrends in einem größeren DataSet darstellen.</span><span class="sxs-lookup"><span data-stu-id="7102d-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="7102d-228">Daher sind die Daten in der Aggregatansicht hier nicht in Echtzeit verfügbar, aber die Daten in der Detailtabellen Ansicht sind möglicherweise geringfügig Diskrepanz zwischen den beiden Ansichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7102d-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="7102d-229">Berichtsansicht für den URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="7102d-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="7102d-230">Der **URL Threat Protection** -Bericht enthält zwei aggregierte Ansichten, die einmal alle vier Stunden aktualisiert werden, sodass Daten für die letzten 90 Tage angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7102d-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="7102d-231">**Aktion zum Schutz vor URLs**: zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klick Vorgangs an:</span><span class="sxs-lookup"><span data-stu-id="7102d-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="7102d-232">**Blockiert** (der Benutzer wurde für die Navigation zur URL gesperrt)</span><span class="sxs-lookup"><span data-stu-id="7102d-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="7102d-233">**Blockiert und durchgeklickt**</span><span class="sxs-lookup"><span data-stu-id="7102d-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="7102d-234">**Durch Klicken während der Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="7102d-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="7102d-235">Ein Klick gibt an, dass der Benutzer auf die Seite blockieren zur böswilligen Website geklickt hat (Administratoren können durch Klicken auf Richtlinien für sichere Links deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="7102d-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="7102d-236">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-237">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-238">Die verfügbaren Klick Schutzaktionen sowie den **zulässigen** Wert (der Benutzer durfte zur URL navigieren).</span><span class="sxs-lookup"><span data-stu-id="7102d-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Aktionsansicht für URL-Klick Schutz im URL Threat Protection-Bericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="7102d-240">**URL-Klick nach Anwendung**: zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:</span><span class="sxs-lookup"><span data-stu-id="7102d-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="7102d-241">**E-Mail-Client**</span><span class="sxs-lookup"><span data-stu-id="7102d-241">**Email client**</span></span>
  - <span data-ttu-id="7102d-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="7102d-242">**PowerPoint**</span></span>
  - <span data-ttu-id="7102d-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="7102d-243">**Word**</span></span>
  - <span data-ttu-id="7102d-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="7102d-244">**Excel**</span></span>
  - <span data-ttu-id="7102d-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="7102d-245">**OneNote**</span></span>
  - <span data-ttu-id="7102d-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="7102d-246">**Visio**</span></span>
  - <span data-ttu-id="7102d-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="7102d-247">**Teams**</span></span>
  - <span data-ttu-id="7102d-248">**Other**</span><span class="sxs-lookup"><span data-stu-id="7102d-248">**Other**</span></span>

  <span data-ttu-id="7102d-249">Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="7102d-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="7102d-250">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="7102d-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7102d-251">Die verfügbaren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7102d-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="7102d-252">Detailtabellen Ansicht für den URL Threat Protection-Bericht</span><span class="sxs-lookup"><span data-stu-id="7102d-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="7102d-253">Wenn Sie auf **Details-Tabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 7 Tage mit den folgenden Details geschehen:</span><span class="sxs-lookup"><span data-stu-id="7102d-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="7102d-254">**Klicken Sie auf Zeit**</span><span class="sxs-lookup"><span data-stu-id="7102d-254">**Click time**</span></span>
- <span data-ttu-id="7102d-255">**Benutzende**</span><span class="sxs-lookup"><span data-stu-id="7102d-255">**User**</span></span>
- <span data-ttu-id="7102d-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="7102d-256">**URL**</span></span>
- <span data-ttu-id="7102d-257">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="7102d-257">**Action**</span></span>
- <span data-ttu-id="7102d-258">**App**</span><span class="sxs-lookup"><span data-stu-id="7102d-258">**App**</span></span>

<span data-ttu-id="7102d-259">Wenn Sie in der Detailtabellen Ansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern, auch nach **Domänen** oder **Empfängern** , die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="7102d-260">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="7102d-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="7102d-261">Zusätzliche Berichte zur Anzeige</span><span class="sxs-lookup"><span data-stu-id="7102d-261">Additional reports to view</span></span>

<span data-ttu-id="7102d-262">Zusätzlich zu den in diesem Thema beschriebenen ATP-Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="7102d-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="7102d-263">Bericht</span><span class="sxs-lookup"><span data-stu-id="7102d-263">Report</span></span>|<span data-ttu-id="7102d-264">Thema</span><span class="sxs-lookup"><span data-stu-id="7102d-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="7102d-265">**Explorer** (ATP-Plan 2) oder **Echt Zeit Erkennungen** (ATP-Plan 1)</span><span class="sxs-lookup"><span data-stu-id="7102d-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="7102d-266">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="7102d-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="7102d-267">**E-Mail-Sicherheitsberichte**wie der Bericht über die häufigsten Absender und Empfänger, der Bericht "Spoof-e-Mail" und der Spam Erkennungs Bericht.</span><span class="sxs-lookup"><span data-stu-id="7102d-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="7102d-268">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7102d-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="7102d-269">**Nachrichtenfluss Berichte**, wie der Weiterleitungs Bericht, der e-Mail-Fluss Statusbericht und der Bericht über die obersten Absender und Empfänger.</span><span class="sxs-lookup"><span data-stu-id="7102d-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="7102d-270">Anzeigen von Nachrichtenfluss Berichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7102d-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="7102d-271">**URL-Ablaufverfolgung für sichere Links** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="7102d-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="7102d-272">Die Ausgabe dieses Cmdlets zeigt die Ergebnisse von Aktionen für sichere Links in den letzten sieben Tagen an.</span><span class="sxs-lookup"><span data-stu-id="7102d-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="7102d-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="7102d-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="7102d-274">**Ergebnisse von e-Mail-Datenverkehr für EoP und ATP** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="7102d-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="7102d-275">Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="7102d-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="7102d-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="7102d-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="7102d-277">**E-Mail-Detailberichte für EoP und ATP-Erkennungen** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="7102d-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="7102d-278">Die Ausgabe dieses Cmdlets enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="7102d-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="7102d-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="7102d-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="7102d-280">Welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="7102d-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="7102d-281">Damit Sie die in diesem Thema beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.</span><span class="sxs-lookup"><span data-stu-id="7102d-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="7102d-282">Für das Security & Compliance Center muss eine der folgenden Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="7102d-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="7102d-283">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="7102d-283">Organization Management</span></span>
  - <span data-ttu-id="7102d-284">Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="7102d-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="7102d-285">Sicherheits Operator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="7102d-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="7102d-286">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="7102d-286">Security Reader</span></span>

- <span data-ttu-id="7102d-287">Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="7102d-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="7102d-288">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="7102d-288">Organization Management</span></span>
  - <span data-ttu-id="7102d-289">Organisationsverwaltung mit Leserechten</span><span class="sxs-lookup"><span data-stu-id="7102d-289">View-only Organization Management</span></span>
  - <span data-ttu-id="7102d-290">Rolle „Empfänger mit Leserechten“</span><span class="sxs-lookup"><span data-stu-id="7102d-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="7102d-291">Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="7102d-291">Compliance Management</span></span>

<span data-ttu-id="7102d-292">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="7102d-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="7102d-293">Berechtigungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7102d-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="7102d-294">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7102d-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="7102d-295">Was geschieht, wenn die Berichte keine Daten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="7102d-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="7102d-296">Wenn Sie keine Daten in ihren ATP-Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="7102d-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="7102d-297">In Ihrer Organisation müssen [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) und Richt [Linien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit ATP-Schutz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7102d-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="7102d-298">Siehe auch [Anti-Spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7102d-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7102d-299">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7102d-299">Related topics</span></span>

[<span data-ttu-id="7102d-300">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7102d-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="7102d-301">Rollen Berechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7102d-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
