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
description: Suchen und Verwenden von Berichten für Microsoft Defender für Office 365 im Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b24249bcbba60bc5340d973567369f534a0178fb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842916"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="5f9a8-103">Anzeigen von Berichten für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="5f9a8-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5f9a8-104">Microsoft Defender für Office 365 Organisationen (beispielsweise Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-ons) enthält eine Reihe von sicherheitsbezogenen Berichten.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="5f9a8-105">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard** Berichte wechseln.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="5f9a8-106">Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="5f9a8-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Das Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="5f9a8-108">Defender for Office 365 File Types Report</span><span class="sxs-lookup"><span data-stu-id="5f9a8-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="5f9a8-109">Der Bericht **Defender for Office 365 File Types Report** zeigt Ihnen den Typ der Dateien an, die von [sicheren Anlagen](atp-safe-attachments.md)als schädlich erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="5f9a8-110">Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während in der Detailansicht nur 10 Tage Filterung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="5f9a8-111">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Defender für Office 365 Dateitypen** aus.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="5f9a8-112">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="5f9a8-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Verteidiger für Office 365-Widget "Dateitypen" im Dashboard "Berichte"](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5f9a8-114">Die Informationen in diesem Bericht sind auch im [Defender für Office 365 Bericht zur Nachrichten Disposition](#defender-for-office-365-message-disposition-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="5f9a8-115">Berichtsansicht für den Verteidiger für Office 365 Dateitypen Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="5f9a8-116">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-116">The following views are available:</span></span>

- <span data-ttu-id="5f9a8-117">**Daten nach: File anzeigen** : das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-117">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="5f9a8-118">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="5f9a8-119">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="5f9a8-120">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="5f9a8-121">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="5f9a8-122">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="5f9a8-123">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="5f9a8-124">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="5f9a8-125">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-125">**Others**</span></span>

  <span data-ttu-id="5f9a8-126">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="5f9a8-128">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-128">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-129">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-130">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="5f9a8-131">**Daten anzeigen nach: Nachricht** : das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-131">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="5f9a8-132">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-132">**Block access**</span></span>
  - <span data-ttu-id="5f9a8-133">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-133">**Messages replaced**</span></span>
  - <span data-ttu-id="5f9a8-134">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-134">**Messages monitored**</span></span>
  - <span data-ttu-id="5f9a8-135">**Durch dynamische e-Mail-Zustellung ersetzt** : Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-135">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="5f9a8-137">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-137">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-138">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-139">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="5f9a8-140">Detailtabellen Ansicht für den Verteidiger für Office 365 Dateitypen Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="5f9a8-141">Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-141">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="5f9a8-142">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5f9a8-143">**Daten nach: File anzeigen** :</span><span class="sxs-lookup"><span data-stu-id="5f9a8-143">**View data by: File** :</span></span>

  - <span data-ttu-id="5f9a8-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-144">**Date**</span></span>
  - <span data-ttu-id="5f9a8-145">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-145">**Recipient address**</span></span>
  - <span data-ttu-id="5f9a8-146">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-146">**Sender address**</span></span>
  - <span data-ttu-id="5f9a8-147">**Nachrichten-ID** : verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-147">**Message ID** : Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="5f9a8-148">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="5f9a8-149">**Datei**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-149">**File**</span></span>

  <span data-ttu-id="5f9a8-150">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-150">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-151">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-152">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="5f9a8-153">**Anzeigen von Daten nach: Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="5f9a8-153">**View data by: Message** :</span></span>

  - <span data-ttu-id="5f9a8-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-154">**Date**</span></span>
  - <span data-ttu-id="5f9a8-155">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-155">**Recipient address**</span></span>
  - <span data-ttu-id="5f9a8-156">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-156">**Sender address**</span></span>
  - <span data-ttu-id="5f9a8-157">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-157">**Message ID**</span></span>
  - <span data-ttu-id="5f9a8-158">**Datei**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-158">**File**</span></span>
  - <span data-ttu-id="5f9a8-159">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-159">**Subject**</span></span>

  <span data-ttu-id="5f9a8-160">Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-160">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-161">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-162">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="5f9a8-163">Klicken Sie auf **Bericht anzeigen** , um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="5f9a8-164">Verteidiger für Office 365 Nachrichten Disposition (Bericht)</span><span class="sxs-lookup"><span data-stu-id="5f9a8-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="5f9a8-165">Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="5f9a8-166">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Defender für Office 365 Nachrichten Disposition** aus.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="5f9a8-167">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="5f9a8-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Defender für Office 365 Nachrichten Dispositions-Widget im Dashboard Berichte](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5f9a8-169">Die Informationen in diesem Bericht stehen auch im [Defender für Office 365 Dateitypen Bericht](#defender-for-office-365-file-types-report)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="5f9a8-170">Berichtsansicht für den Verteidiger für Office 365 Bericht zur Nachrichten Disposition</span><span class="sxs-lookup"><span data-stu-id="5f9a8-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="5f9a8-171">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-171">The following views are available:</span></span>

- <span data-ttu-id="5f9a8-172">**Daten anzeigen nach: Nachricht** : das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-172">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="5f9a8-173">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-173">**Block access**</span></span>
  - <span data-ttu-id="5f9a8-174">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-174">**Messages replaced**</span></span>
  - <span data-ttu-id="5f9a8-175">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-175">**Messages monitored**</span></span>
  - <span data-ttu-id="5f9a8-176">**Durch dynamische e-Mail-Zustellung ersetzt** : Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-176">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="5f9a8-178">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-178">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-179">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-180">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="5f9a8-181">**Daten nach: File anzeigen** : das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-181">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="5f9a8-182">**Böswillige Excel-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="5f9a8-183">**Böswillige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="5f9a8-184">**Böswillige PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="5f9a8-185">**Böswillige PowerPoint-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="5f9a8-186">**Böswillige URLs**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="5f9a8-187">**Böswillige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="5f9a8-188">**Böswillige ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="5f9a8-189">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-189">**Others**</span></span>

  <span data-ttu-id="5f9a8-190">Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Datei Ansicht im Defender für Office 365 Dateitypen Bericht](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="5f9a8-192">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-192">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-193">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-194">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="5f9a8-195">Detailtabellen Ansicht für den Verteidiger für Office 365 Bericht zur Nachrichten Disposition</span><span class="sxs-lookup"><span data-stu-id="5f9a8-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="5f9a8-196">Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-196">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="5f9a8-197">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5f9a8-198">**Anzeigen von Daten nach: Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="5f9a8-198">**View data by: Message** :</span></span>

  - <span data-ttu-id="5f9a8-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-199">**Date**</span></span>
  - <span data-ttu-id="5f9a8-200">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-200">**Recipient address**</span></span>
  - <span data-ttu-id="5f9a8-201">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-201">**Sender address**</span></span>
  - <span data-ttu-id="5f9a8-202">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-202">**Message ID**</span></span>
  - <span data-ttu-id="5f9a8-203">**Datei**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-203">**File**</span></span>
  - <span data-ttu-id="5f9a8-204">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-204">**Subject**</span></span>

  <span data-ttu-id="5f9a8-205">Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-205">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-206">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-207">Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="5f9a8-208">**Daten nach: File anzeigen** :</span><span class="sxs-lookup"><span data-stu-id="5f9a8-208">**View data by: File** :</span></span>

  - <span data-ttu-id="5f9a8-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-209">**Date**</span></span>
  - <span data-ttu-id="5f9a8-210">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-210">**Recipient address**</span></span>
  - <span data-ttu-id="5f9a8-211">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-211">**Sender address**</span></span>
  - <span data-ttu-id="5f9a8-212">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-212">**Message ID**</span></span>
  - <span data-ttu-id="5f9a8-213">**Datei**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-213">**File**</span></span>

  <span data-ttu-id="5f9a8-214">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-214">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-215">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-216">Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="5f9a8-217">Klicken Sie auf **Bericht anzeigen** , um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="5f9a8-218">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-218">Threat protection status report</span></span>

<span data-ttu-id="5f9a8-219">Der **Statusbericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EoP) und Microsoft Defender für Office 365 erkannt und blockiert wurden, zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5f9a8-220">Weitere Informationen finden Sie unter [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="5f9a8-221">URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-221">URL threat protection report</span></span>

<span data-ttu-id="5f9a8-222">Der **Bericht über den URL-Bedrohungsschutz** bietet zusammenfassende und Trend Ansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen von [sicheren Links](atp-safe-links.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="5f9a8-223">In diesem Bericht werden keine klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links angewendet die Option **Benutzerklicks nicht nachverfolgen** aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="5f9a8-224">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **URL-Schutzbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="5f9a8-225">Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="5f9a8-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget "URL Protection-Bericht" im Dashboard "Berichte"](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5f9a8-227">Hierbei handelt es sich um einen *Schutz Trendbericht* , was bedeutet, dass Datentrends in einem größeren DataSet darstellen.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-227">This is a *protection trend report* , meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="5f9a8-228">Daher sind die Daten in der Aggregatansicht hier nicht in Echtzeit verfügbar, aber die Daten in der Detailtabellen Ansicht sind möglicherweise geringfügig Diskrepanz zwischen den beiden Ansichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="5f9a8-229">Berichtsansicht für den URL-Bedrohungsschutz Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="5f9a8-230">Der **URL Threat Protection** -Bericht enthält zwei aggregierte Ansichten, die einmal alle vier Stunden aktualisiert werden, sodass Daten für die letzten 90 Tage angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="5f9a8-231">**Aktion zum Schutz vor URLs** : zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klick Vorgangs an:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-231">**URL click protection action** : Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="5f9a8-232">**Blockiert** (der Benutzer wurde für die Navigation zur URL gesperrt)</span><span class="sxs-lookup"><span data-stu-id="5f9a8-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="5f9a8-233">**Blockiert und durchgeklickt**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="5f9a8-234">**Durch Klicken während der Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="5f9a8-235">Ein Klick gibt an, dass der Benutzer auf die Seite blockieren zur böswilligen Website geklickt hat (Administratoren können durch Klicken auf Richtlinien für sichere Links deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="5f9a8-236">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-236">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-237">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-238">Die verfügbaren Klick Schutzaktionen sowie den **zulässigen** Wert (der Benutzer durfte zur URL navigieren).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Aktionsansicht für URL-Klick Schutz im URL Threat Protection-Bericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="5f9a8-240">**URL-Klick nach Anwendung** : zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-240">**URL click by application** : Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="5f9a8-241">**E-Mail-Client**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-241">**Email client**</span></span>
  - <span data-ttu-id="5f9a8-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-242">**PowerPoint**</span></span>
  - <span data-ttu-id="5f9a8-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-243">**Word**</span></span>
  - <span data-ttu-id="5f9a8-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-244">**Excel**</span></span>
  - <span data-ttu-id="5f9a8-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-245">**OneNote**</span></span>
  - <span data-ttu-id="5f9a8-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-246">**Visio**</span></span>
  - <span data-ttu-id="5f9a8-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-247">**Teams**</span></span>
  - <span data-ttu-id="5f9a8-248">**Other**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-248">**Other**</span></span>

  <span data-ttu-id="5f9a8-249">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-249">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5f9a8-250">**Start Datum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5f9a8-251">Die verfügbaren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="5f9a8-252">Detailtabellen Ansicht für den URL Threat Protection-Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="5f9a8-253">Wenn Sie auf **Details-Tabelle anzeigen** klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 7 Tage mit den folgenden Details geschehen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-253">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="5f9a8-254">**Klicken Sie auf Zeit**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-254">**Click time**</span></span>
- <span data-ttu-id="5f9a8-255">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-255">**User**</span></span>
- <span data-ttu-id="5f9a8-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-256">**URL**</span></span>
- <span data-ttu-id="5f9a8-257">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-257">**Action**</span></span>
- <span data-ttu-id="5f9a8-258">**App**</span><span class="sxs-lookup"><span data-stu-id="5f9a8-258">**App**</span></span>

<span data-ttu-id="5f9a8-259">Wenn Sie in der Detailtabellen Ansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern, auch nach **Domänen** oder **Empfängern** , die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="5f9a8-260">Klicken Sie auf **Bericht anzeigen** , um wieder zur Berichtsansicht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="5f9a8-261">Zusätzliche Berichte zur Anzeige</span><span class="sxs-lookup"><span data-stu-id="5f9a8-261">Additional reports to view</span></span>

<span data-ttu-id="5f9a8-262">Zusätzlich zu den in diesem Thema beschriebenen Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-262">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="5f9a8-263">Bericht</span><span class="sxs-lookup"><span data-stu-id="5f9a8-263">Report</span></span>|<span data-ttu-id="5f9a8-264">Thema</span><span class="sxs-lookup"><span data-stu-id="5f9a8-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="5f9a8-265">**Explorer** (Microsoft Defender für Office 365 Plan 2) oder **Echtzeiterkennung** (Microsoft Defender für Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="5f9a8-265">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="5f9a8-266">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="5f9a8-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="5f9a8-267">**E-Mail-Sicherheitsberichte** wie der Bericht über die häufigsten Absender und Empfänger, der Bericht "Spoof-e-Mail" und der Spam Erkennungs Bericht.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-267">**Email security reports** , such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="5f9a8-268">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5f9a8-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="5f9a8-269">**Nachrichtenfluss Berichte** , wie der Weiterleitungs Bericht, der e-Mail-Fluss Statusbericht und der Bericht über die obersten Absender und Empfänger.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-269">**Mail flow reports** , such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="5f9a8-270">Anzeigen von Nachrichtenfluss Berichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5f9a8-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="5f9a8-271">**URL-Ablaufverfolgung für sichere Links** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="5f9a8-272">Die Ausgabe dieses Cmdlets zeigt die Ergebnisse von Aktionen für sichere Links in den letzten sieben Tagen an.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="5f9a8-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="5f9a8-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="5f9a8-274">**Ergebnisse des e-Mail-Verkehrs für EoP und Microsoft Defender für Office 365** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-274">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="5f9a8-275">Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="5f9a8-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="5f9a8-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="5f9a8-277">**E-Mail-Detailberichte für EoP und Defender für Office 365 Erkennungen** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-277">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="5f9a8-278">Die Ausgabe dieses Cmdlets enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="5f9a8-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="5f9a8-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="5f9a8-280">Welche Berechtigungen sind erforderlich, um den Verteidiger für Office 365 Berichte anzuzeigen?</span><span class="sxs-lookup"><span data-stu-id="5f9a8-280">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="5f9a8-281">Damit Sie die in diesem Thema beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="5f9a8-282">Für das Security & Compliance Center muss eine der folgenden Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="5f9a8-283">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5f9a8-283">Organization Management</span></span>
  - <span data-ttu-id="5f9a8-284">Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="5f9a8-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5f9a8-285">Sicherheits Operator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="5f9a8-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5f9a8-286">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="5f9a8-286">Security Reader</span></span>

- <span data-ttu-id="5f9a8-287">Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="5f9a8-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="5f9a8-288">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5f9a8-288">Organization Management</span></span>
  - <span data-ttu-id="5f9a8-289">Organisationsverwaltung mit Leserechten</span><span class="sxs-lookup"><span data-stu-id="5f9a8-289">View-only Organization Management</span></span>
  - <span data-ttu-id="5f9a8-290">Rolle „Empfänger mit Leserechten“</span><span class="sxs-lookup"><span data-stu-id="5f9a8-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="5f9a8-291">Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="5f9a8-291">Compliance Management</span></span>

<span data-ttu-id="5f9a8-292">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="5f9a8-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="5f9a8-293">Berechtigungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5f9a8-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="5f9a8-294">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5f9a8-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5f9a8-295">Was geschieht, wenn die Berichte keine Daten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="5f9a8-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5f9a8-296">Wenn für Office 365 Berichte keine Daten in Ihrem Defender angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-296">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5f9a8-297">In Ihrer Organisation müssen [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) und Richt [Linien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit der Verteidiger Office 365 Schutz gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="5f9a8-298">Siehe auch [Anti-Spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f9a8-299">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5f9a8-299">Related topics</span></span>

[<span data-ttu-id="5f9a8-300">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5f9a8-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="5f9a8-301">Rollen Berechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5f9a8-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
