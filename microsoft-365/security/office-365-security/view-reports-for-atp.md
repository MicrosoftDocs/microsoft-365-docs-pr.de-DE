---
title: Anzeigen von Berichten für Defender für Office 365
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
description: Suchen und Verwenden von Berichten für Microsoft Defender für Office 365 im Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5efaef018c78bd161c9cde81af36be92173479ae
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561727"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="18376-103">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="18376-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="18376-104">Microsoft Defender für Office 365 Organisationen (beispielsweise Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-ons) enthält eine Reihe von sicherheitsbezogenen Berichten.</span><span class="sxs-lookup"><span data-stu-id="18376-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="18376-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard** Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="18376-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="18376-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="18376-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Das Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="18376-108">Defender for Office 365 File Types Report</span><span class="sxs-lookup"><span data-stu-id="18376-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="18376-109">Der Bericht **Defender for Office 365 File Types Report** zeigt Ihnen den Typ der Dateien an, die von [sicheren Anlagen](atp-safe-attachments.md)als schädlich erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="18376-110">Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während in der Detailansicht nur 10 Tage Filterung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="18376-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="18376-111">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Defender für Office 365 Dateitypen** aus.</span><span class="sxs-lookup"><span data-stu-id="18376-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="18376-112">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="18376-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Verteidiger für Office 365-Widget "Dateitypen" im Dashboard "Berichte"](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="18376-114">Die Informationen in diesem Bericht sind auch im [Defender für Office 365 Bericht zur Nachrichten Disposition](#defender-for-office-365-message-disposition-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18376-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="18376-115">Berichtsansicht für den Verteidiger für Office 365 Dateitypen Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="18376-116">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="18376-116">The following views are available:</span></span>

- <span data-ttu-id="18376-117">**Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="18376-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="18376-118">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="18376-119">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="18376-120">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="18376-121">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="18376-122">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="18376-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="18376-123">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="18376-124">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="18376-125">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="18376-125">**Others**</span></span>

  <span data-ttu-id="18376-126">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="18376-128">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-129">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-130">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="18376-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="18376-131">**Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="18376-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="18376-132">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="18376-132">**Block access**</span></span>
  - <span data-ttu-id="18376-133">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="18376-133">**Messages replaced**</span></span>
  - <span data-ttu-id="18376-134">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="18376-134">**Messages monitored**</span></span>
  - <span data-ttu-id="18376-135">**Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="18376-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="18376-137">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-138">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-139">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="18376-140">Detailtabellen Ansicht für den Verteidiger für Office 365 Dateitypen Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="18376-141">Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="18376-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="18376-142">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="18376-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="18376-143">**Daten nach: File anzeigen**:</span><span class="sxs-lookup"><span data-stu-id="18376-143">**View data by: File**:</span></span>

  - <span data-ttu-id="18376-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="18376-144">**Date**</span></span>
  - <span data-ttu-id="18376-145">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="18376-145">**Recipient address**</span></span>
  - <span data-ttu-id="18376-146">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="18376-146">**Sender address**</span></span>
  - <span data-ttu-id="18376-147">**Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="18376-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="18376-148">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="18376-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="18376-149">**Datei**</span><span class="sxs-lookup"><span data-stu-id="18376-149">**File**</span></span>

  <span data-ttu-id="18376-150">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-151">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-152">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="18376-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="18376-153">**Anzeigen von Daten nach: Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="18376-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="18376-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="18376-154">**Date**</span></span>
  - <span data-ttu-id="18376-155">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="18376-155">**Recipient address**</span></span>
  - <span data-ttu-id="18376-156">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="18376-156">**Sender address**</span></span>
  - <span data-ttu-id="18376-157">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="18376-157">**Message ID**</span></span>
  - <span data-ttu-id="18376-158">**Datei**</span><span class="sxs-lookup"><span data-stu-id="18376-158">**File**</span></span>
  - <span data-ttu-id="18376-159">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="18376-159">**Subject**</span></span>

  <span data-ttu-id="18376-160">Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="18376-161">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-162">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="18376-163">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="18376-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="18376-164">Verteidiger für Office 365 Nachrichten Disposition (Bericht)</span><span class="sxs-lookup"><span data-stu-id="18376-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="18376-165">Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="18376-166">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Defender für Office 365 Nachrichten Disposition** aus.</span><span class="sxs-lookup"><span data-stu-id="18376-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="18376-167">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="18376-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Defender für Office 365 Nachrichten Dispositions-Widget im Dashboard Berichte](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="18376-169">Die Informationen in diesem Bericht stehen auch im [Defender für Office 365 Dateitypen Bericht](#defender-for-office-365-file-types-report)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="18376-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="18376-170">Berichtsansicht für den Verteidiger für Office 365 Bericht zur Nachrichten Disposition</span><span class="sxs-lookup"><span data-stu-id="18376-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="18376-171">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="18376-171">The following views are available:</span></span>

- <span data-ttu-id="18376-172">**Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="18376-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="18376-173">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="18376-173">**Block access**</span></span>
  - <span data-ttu-id="18376-174">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="18376-174">**Messages replaced**</span></span>
  - <span data-ttu-id="18376-175">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="18376-175">**Messages monitored**</span></span>
  - <span data-ttu-id="18376-176">**Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="18376-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="18376-178">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-179">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-180">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="18376-181">**Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="18376-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="18376-182">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="18376-183">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="18376-184">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="18376-185">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="18376-186">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="18376-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="18376-187">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="18376-188">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="18376-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="18376-189">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="18376-189">**Others**</span></span>

  <span data-ttu-id="18376-190">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="18376-192">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-193">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-194">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="18376-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="18376-195">Detailtabellen Ansicht für den Verteidiger für Office 365 Bericht zur Nachrichten Disposition</span><span class="sxs-lookup"><span data-stu-id="18376-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="18376-196">Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="18376-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="18376-197">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="18376-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="18376-198">**Anzeigen von Daten nach: Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="18376-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="18376-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="18376-199">**Date**</span></span>
  - <span data-ttu-id="18376-200">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="18376-200">**Recipient address**</span></span>
  - <span data-ttu-id="18376-201">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="18376-201">**Sender address**</span></span>
  - <span data-ttu-id="18376-202">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="18376-202">**Message ID**</span></span>
  - <span data-ttu-id="18376-203">**Datei**</span><span class="sxs-lookup"><span data-stu-id="18376-203">**File**</span></span>
  - <span data-ttu-id="18376-204">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="18376-204">**Subject**</span></span>

  <span data-ttu-id="18376-205">Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="18376-206">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-207">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="18376-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="18376-208">**Daten nach: File anzeigen**:</span><span class="sxs-lookup"><span data-stu-id="18376-208">**View data by: File**:</span></span>

  - <span data-ttu-id="18376-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="18376-209">**Date**</span></span>
  - <span data-ttu-id="18376-210">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="18376-210">**Recipient address**</span></span>
  - <span data-ttu-id="18376-211">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="18376-211">**Sender address**</span></span>
  - <span data-ttu-id="18376-212">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="18376-212">**Message ID**</span></span>
  - <span data-ttu-id="18376-213">**Datei**</span><span class="sxs-lookup"><span data-stu-id="18376-213">**File**</span></span>

  <span data-ttu-id="18376-214">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-215">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-216">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="18376-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="18376-217">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="18376-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="18376-218">Bericht über die e-Mail-Wartezeit</span><span class="sxs-lookup"><span data-stu-id="18376-218">Mail latency report</span></span>

<span data-ttu-id="18376-219">Der **Bericht über die e-Mail-Wartezeit** zeigt eine aggregierte Ansicht der in Ihrer Organisation erlebten e-Mail-Zustellung und der detonations Wartezeit.</span><span class="sxs-lookup"><span data-stu-id="18376-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="18376-220">E-Mail-Zustellungszeiten im Dienst sind von einer Reihe von Faktoren betroffen, und die absolute Lieferzeit in Sekunden ist oft kein guter Indikator für Erfolg oder ein Problem.</span><span class="sxs-lookup"><span data-stu-id="18376-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="18376-221">Eine langsame Lieferzeit an einem Tag kann als durchschnittliche Zustellungszeit an einem anderen Tag betrachtet werden oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="18376-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="18376-222">Der **Bericht über die e-Mail-Wartezeit** versucht, die Nachrichtenzustellung basierend auf statistischen Daten über die beobachteten Zustellungszeiten anderer Nachrichten zu qualifizieren:</span><span class="sxs-lookup"><span data-stu-id="18376-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="18376-223">**50. Perzentil**: Dies ist die Mitte für Nachrichten Zustellungszeiten.</span><span class="sxs-lookup"><span data-stu-id="18376-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="18376-224">Sie können diesen Wert als durchschnittliche Zustellungsdauer ansehen.</span><span class="sxs-lookup"><span data-stu-id="18376-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="18376-225">**90. Perzentil**: Dies deutet auf eine hohe Wartezeit für die Nachrichtenzustellung hin.</span><span class="sxs-lookup"><span data-stu-id="18376-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="18376-226">Nur 10% der Nachrichten dauerte länger als dieser Wert zu liefern.</span><span class="sxs-lookup"><span data-stu-id="18376-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="18376-227">**99th Perzentil**: Dies gibt die höchste Wartezeit für die Nachrichtenzustellung an.</span><span class="sxs-lookup"><span data-stu-id="18376-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="18376-228">Client seitige und Netzwerkwartezeit sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="18376-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="18376-229">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** - \> **Dashboard** , und wählen Sie **e-Mail-Latenz Bericht** aus.</span><span class="sxs-lookup"><span data-stu-id="18376-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="18376-230">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="18376-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![E-Mail-Latenz Bericht-Widget im Dashboard Berichte](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="18376-232">Berichtsansicht für den Bericht über die e-Mail-Wartezeit</span><span class="sxs-lookup"><span data-stu-id="18376-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="18376-233">Wenn Sie den Bericht öffnen, ist die Registerkarte **50% Perzentil** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="18376-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="18376-234">Diese Ansicht enthält standardmäßig ein Diagramm, das mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="18376-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="18376-235">**Datum**: die letzten 7 Tage</span><span class="sxs-lookup"><span data-stu-id="18376-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="18376-236">**Nachrichtenansicht**:</span><span class="sxs-lookup"><span data-stu-id="18376-236">**Message View**:</span></span>
  - <span data-ttu-id="18376-237">Gezündete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="18376-237">Detonated messages</span></span>

<span data-ttu-id="18376-238">In diesem Diagramm werden Nachrichten angezeigt, die in die folgenden Kategorien aufgeteilt sind:</span><span class="sxs-lookup"><span data-stu-id="18376-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="18376-239">**E-Mail-Zustellungs Wartezeit**</span><span class="sxs-lookup"><span data-stu-id="18376-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="18376-240">**Detonations Wartezeit**</span><span class="sxs-lookup"><span data-stu-id="18376-240">**Detonation latency**</span></span>

<span data-ttu-id="18376-241">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, wird eine Aufschlüsselung der Wartezeit in jeder Kategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18376-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Bericht über die e-Mail-Wartezeit](../../media/mail-latency-report.png)

<span data-ttu-id="18376-243">Wenn Sie in der Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="18376-244">Alle Nachrichten</span><span class="sxs-lookup"><span data-stu-id="18376-244">All messages</span></span>
- <span data-ttu-id="18376-245">Nachrichten, die Anlagen oder URLs enthalten</span><span class="sxs-lookup"><span data-stu-id="18376-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="18376-246">Wenn Sie auf die Registerkarte **90% Perzentil** oder auf die Registerkarte **99th Perzentil** klicken, werden die gleichen Standardfilter aus der Ansicht **50% Perzentil** verwendet.</span><span class="sxs-lookup"><span data-stu-id="18376-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="18376-247">Detailtabellen Ansicht für den Bericht über die e-Mail-Wartezeit</span><span class="sxs-lookup"><span data-stu-id="18376-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="18376-248">Die folgenden Informationen werden in der Detailtabellen Ansicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="18376-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="18376-249">**Date**</span><span class="sxs-lookup"><span data-stu-id="18376-249">**Date**</span></span>
- <span data-ttu-id="18376-250">**Quantile**</span><span class="sxs-lookup"><span data-stu-id="18376-250">**Percentiles**</span></span>
- <span data-ttu-id="18376-251">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="18376-251">**Message count**</span></span>
- <span data-ttu-id="18376-252">**Gesamtwartezeit**</span><span class="sxs-lookup"><span data-stu-id="18376-252">**Overall latency**</span></span>

![Details zum Bericht über e-Mail-Wartezeit](../../media/mail-latency-report-details.png)

<span data-ttu-id="18376-254">Das obige zeigt, dass die durchschnittliche Wartezeit für alle zugestellten und gezündeten Nachrichten am 14. November **108,033** Sekunden betrug.</span><span class="sxs-lookup"><span data-stu-id="18376-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="18376-255">Die Detailtabelle enthält dieselben Informationen auf jeder Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="18376-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="18376-256">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="18376-256">Threat protection status report</span></span>

<span data-ttu-id="18376-257">Der **Statusbericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EoP) und Microsoft Defender für Office 365 erkannt und blockiert wurden, zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18376-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="18376-258">Weitere Informationen finden Sie unter [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="18376-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="18376-259">URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-259">URL threat protection report</span></span>

<span data-ttu-id="18376-260">Der **Bericht über den URL-Bedrohungsschutz** bietet zusammenfassende und Trend Ansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen von [sicheren Links](atp-safe-links.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18376-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="18376-261">In diesem Bericht werden keine klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links angewendet die Option **Benutzerklicks nicht nachverfolgen** aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="18376-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="18376-262">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **URL-Schutzbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="18376-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="18376-263">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="18376-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget "URL Protection-Bericht" im Dashboard "Berichte"](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="18376-265">Hierbei handelt es sich um einen *Schutz Trendbericht*, was bedeutet, dass Datentrends in einem größeren DataSet darstellen.</span><span class="sxs-lookup"><span data-stu-id="18376-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="18376-266">Daher sind die Daten in der Aggregatansicht hier nicht in Echtzeit verfügbar, aber die Daten in der Detailtabellen Ansicht sind möglicherweise geringfügig Diskrepanz zwischen den beiden Ansichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18376-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="18376-267">Berichtsansicht für den URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="18376-268">Der **URL Threat Protection** -Bericht enthält zwei aggregierte Ansichten, die einmal alle vier Stunden aktualisiert werden, sodass Daten für die letzten 90 Tage angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="18376-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="18376-269">**Aktion zum Schutz vor URLs**: zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klick Vorgangs an:</span><span class="sxs-lookup"><span data-stu-id="18376-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="18376-270">**Blockiert** (der Benutzer wurde für die Navigation zur URL gesperrt)</span><span class="sxs-lookup"><span data-stu-id="18376-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="18376-271">**Blockiert und durchgeklickt**</span><span class="sxs-lookup"><span data-stu-id="18376-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="18376-272">**Durch Klicken während der Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="18376-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="18376-273">Ein Klick gibt an, dass der Benutzer auf die Seite blockieren zur böswilligen Website geklickt hat (Administratoren können durch Klicken auf Richtlinien für sichere Links deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="18376-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="18376-274">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-275">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-276">Die verfügbaren Klick Schutzaktionen sowie den **zulässigen** Wert (der Benutzer durfte zur URL navigieren).</span><span class="sxs-lookup"><span data-stu-id="18376-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Aktionsansicht für URL-Klick Schutz im URL Threat Protection-Bericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="18376-278">**URL-Klick nach Anwendung**: zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:</span><span class="sxs-lookup"><span data-stu-id="18376-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="18376-279">**E-Mail-Client**</span><span class="sxs-lookup"><span data-stu-id="18376-279">**Email client**</span></span>
  - <span data-ttu-id="18376-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="18376-280">**PowerPoint**</span></span>
  - <span data-ttu-id="18376-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="18376-281">**Word**</span></span>
  - <span data-ttu-id="18376-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="18376-282">**Excel**</span></span>
  - <span data-ttu-id="18376-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="18376-283">**OneNote**</span></span>
  - <span data-ttu-id="18376-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="18376-284">**Visio**</span></span>
  - <span data-ttu-id="18376-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="18376-285">**Teams**</span></span>
  - <span data-ttu-id="18376-286">**Other**</span><span class="sxs-lookup"><span data-stu-id="18376-286">**Other**</span></span>

  <span data-ttu-id="18376-287">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="18376-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="18376-288">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="18376-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="18376-289">Die verfügbaren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="18376-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="18376-290">Detailtabellen Ansicht für den URL Threat Protection-Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="18376-291">Wenn Sie auf **Details-Tabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 7 Tage mit den folgenden Details geschehen:</span><span class="sxs-lookup"><span data-stu-id="18376-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="18376-292">**Klicken Sie auf Zeit**</span><span class="sxs-lookup"><span data-stu-id="18376-292">**Click time**</span></span>
- <span data-ttu-id="18376-293">**Benutzende**</span><span class="sxs-lookup"><span data-stu-id="18376-293">**User**</span></span>
- <span data-ttu-id="18376-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="18376-294">**URL**</span></span>
- <span data-ttu-id="18376-295">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="18376-295">**Action**</span></span>
- <span data-ttu-id="18376-296">**App**</span><span class="sxs-lookup"><span data-stu-id="18376-296">**App**</span></span>

<span data-ttu-id="18376-297">Wenn Sie in der Detailtabellen Ansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern, auch nach **Domänen** oder **Empfängern** , die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="18376-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="18376-298">Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="18376-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="18376-299">Zusätzliche Berichte zur Anzeige</span><span class="sxs-lookup"><span data-stu-id="18376-299">Additional reports to view</span></span>

<span data-ttu-id="18376-300">Zusätzlich zu den in diesem Thema beschriebenen Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="18376-300">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="18376-301">Bericht</span><span class="sxs-lookup"><span data-stu-id="18376-301">Report</span></span>|<span data-ttu-id="18376-302">Thema</span><span class="sxs-lookup"><span data-stu-id="18376-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="18376-303">**Explorer** (Microsoft Defender für Office 365 Plan 2) oder **Echtzeiterkennung** (Microsoft Defender für Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="18376-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="18376-304">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="18376-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="18376-305">**E-Mail-Sicherheitsberichte** wie der Bericht über die häufigsten Absender und Empfänger, der Bericht "Spoof-e-Mail" und der Spam Erkennungs Bericht.</span><span class="sxs-lookup"><span data-stu-id="18376-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="18376-306">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18376-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="18376-307">**Nachrichtenfluss Berichte**, wie der Weiterleitungs Bericht, der e-Mail-Fluss Statusbericht und der Bericht über die obersten Absender und Empfänger.</span><span class="sxs-lookup"><span data-stu-id="18376-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="18376-308">Anzeigen von Nachrichtenfluss Berichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18376-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="18376-309">**URL-Ablaufverfolgung für sichere Links** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="18376-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="18376-310">Die Ausgabe dieses Cmdlets zeigt die Ergebnisse von Aktionen für sichere Links in den letzten sieben Tagen an.</span><span class="sxs-lookup"><span data-stu-id="18376-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="18376-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="18376-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="18376-312">**Ergebnisse des e-Mail-Verkehrs für EoP und Microsoft Defender für Office 365** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="18376-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="18376-313">Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="18376-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="18376-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="18376-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="18376-315">**E-Mail-Detailberichte für EoP und Defender für Office 365 Erkennungen** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="18376-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="18376-316">Die Ausgabe dieses Cmdlets enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="18376-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="18376-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="18376-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="18376-318">Welche Berechtigungen sind erforderlich, um den Verteidiger für Office 365 Berichte anzuzeigen?</span><span class="sxs-lookup"><span data-stu-id="18376-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="18376-319">Damit Sie die in diesem Thema beschriebenen Berichte anzeigen und verwenden können, **müssen Sie sowohl dem Security & Compliance Center als auch dem Exchange Admin Center eine entsprechende Rolle zugewiesen haben**.</span><span class="sxs-lookup"><span data-stu-id="18376-319">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security & Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="18376-320">Für das Security & Compliance Center muss eine der folgenden Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="18376-320">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="18376-321">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="18376-321">Organization Management</span></span>
  - <span data-ttu-id="18376-322">Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="18376-322">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="18376-323">Sicherheits Operator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="18376-323">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="18376-324">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="18376-324">Security Reader</span></span>

- <span data-ttu-id="18376-325">Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="18376-325">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="18376-326">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="18376-326">Organization Management</span></span>
  - <span data-ttu-id="18376-327">Organisationsverwaltung mit Leserechten</span><span class="sxs-lookup"><span data-stu-id="18376-327">View-only Organization Management</span></span>
  - <span data-ttu-id="18376-328">Rolle „Empfänger mit Leserechten“</span><span class="sxs-lookup"><span data-stu-id="18376-328">View-Only Recipients role</span></span>
  - <span data-ttu-id="18376-329">Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="18376-329">Compliance Management</span></span>

<span data-ttu-id="18376-330">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="18376-330">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="18376-331">Berechtigungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18376-331">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="18376-332">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="18376-332">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="18376-333">Was geschieht, wenn die Berichte keine Daten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="18376-333">What if the reports aren't showing data?</span></span>

<span data-ttu-id="18376-334">Wenn für Office 365 Berichte keine Daten in Ihrem Defender angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="18376-334">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="18376-335">In Ihrer Organisation müssen [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) und Richt [Linien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit der Verteidiger Office 365 Schutz gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="18376-335">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="18376-336">Siehe auch [Anti-Spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="18376-336">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18376-337">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="18376-337">Related topics</span></span>

[<span data-ttu-id="18376-338">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18376-338">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="18376-339">Rollen Berechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="18376-339">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
