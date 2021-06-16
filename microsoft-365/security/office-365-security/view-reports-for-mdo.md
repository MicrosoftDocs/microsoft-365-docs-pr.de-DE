---
title: Anzeigen von Defender für Office 365 Berichte im Berichtsdashboard
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Suchen und Verwenden von Berichten für Microsoft Defender für Office 365 im Microsoft 365 Defender-Portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930203"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f4fe9-103">Anzeigen von Defender für Office 365 Berichte im Dashboard "Berichte" im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="f4fe9-103">View Defender for Office 365 reports in the Reports dashboard in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4fe9-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-104">**Applies to**</span></span>
- [<span data-ttu-id="f4fe9-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f4fe9-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f4fe9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4fe9-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f4fe9-107">Microsoft Defender für Office 365 Organisationen (z. B. Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-Ons) enthalten eine Vielzahl von sicherheitsrelevanten Berichten.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="f4fe9-108">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie berichte  \> **E-Mail-Zusammenarbeitsberichte** für \> **E-Mail-Zusammenarbeit melden.**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email collaboration** \> **Email collaboration reports**.</span></span> <span data-ttu-id="f4fe9-109">Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="f4fe9-109">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Das Dashboard "Berichte" im Microsoft 365 Defender-Portal](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="f4fe9-111">Defender für Office 365-Bericht zu Dateitypen</span><span class="sxs-lookup"><span data-stu-id="f4fe9-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="f4fe9-112">Der **Bericht "Defender für Office 365-Dateitypen"** zeigt Ihnen den Typ der Dateien an, die von sicheren Anlagen als [bösartig](safe-attachments.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](safe-attachments.md).</span></span>

 <span data-ttu-id="f4fe9-113">Die Aggregatansicht des Berichts ermöglicht das Filtern von 90 Tagen, während die Detailansicht nur 10 Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="f4fe9-114">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie Defender für **Office 365 Dateitypen aus.**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-114">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="f4fe9-115">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="f4fe9-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Defender für Office 365-Dateitypen-Widget im Berichtsdashboard](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f4fe9-117">Die Informationen in diesem Bericht sind auch im [Defender for Office 365 Message Disposition Report](#defender-for-office-365-message-disposition-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="f4fe9-118">Berichtsansicht für den Bericht "Defender für Office 365"-Dateitypen</span><span class="sxs-lookup"><span data-stu-id="f4fe9-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="f4fe9-119">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-119">The following views are available:</span></span>

- <span data-ttu-id="f4fe9-120">**Anzeigen von Daten nach: Datei:** Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f4fe9-121">**Bösartige Excel Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="f4fe9-122">**Bösartige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="f4fe9-123">**Schädliche PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="f4fe9-124">**Schädliche PowerPoint Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="f4fe9-125">**Bösartige URLs**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="f4fe9-126">**Bösartige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="f4fe9-127">**Schädliche ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="f4fe9-128">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-128">**Others**</span></span>

  <span data-ttu-id="f4fe9-129">Wenn Sie mit dem Mauszeiger über einen bestimmten Tag (Datenpunkt) zeigen, sehen Sie die Aufschlüsselung der Arten von schädlichen Dateien, die von [sicheren Anlagen](safe-attachments.md) und [dem Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Dateiansicht im Bericht "Defender für Office 365"-Dateitypen](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="f4fe9-131">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-132">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-133">Die gleichen Dateitypwerte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="f4fe9-134">**Anzeigen von Daten nach: Meldung:** Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f4fe9-135">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-135">**Block access**</span></span>
  - <span data-ttu-id="f4fe9-136">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-136">**Messages replaced**</span></span>
  - <span data-ttu-id="f4fe9-137">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-137">**Messages monitored**</span></span>
  - <span data-ttu-id="f4fe9-138">**Ersetzt durch dynamische E-Mail-Zustellung:** Weitere Informationen finden Sie unter ["Dynamische Zustellung in Richtlinien für sichere Anlagen".](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Bericht "Defender für Office 365"-Dateitypen](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="f4fe9-140">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-141">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-142">Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und der zusätzliche **übergebene** Nachrichtenwert.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="f4fe9-143">Detailtabellenansicht für den Bericht "Defender für Office 365"-Dateitypen</span><span class="sxs-lookup"><span data-stu-id="f4fe9-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="f4fe9-144">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, bietet der Bericht eine Nahezu-Echtzeitansicht aller Klicks, die innerhalb der Organisation während der letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="f4fe9-145">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f4fe9-146">**Anzeigen von Daten nach: Datei:**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-146">**View data by: File**:</span></span>

  - <span data-ttu-id="f4fe9-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-147">**Date**</span></span>
  - <span data-ttu-id="f4fe9-148">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-148">**Recipient address**</span></span>
  - <span data-ttu-id="f4fe9-149">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-149">**Sender address**</span></span>
  - <span data-ttu-id="f4fe9-150">**Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="f4fe9-151">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="f4fe9-152">**Datei**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-152">**File**</span></span>

  <span data-ttu-id="f4fe9-153">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-154">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-155">Die gleichen Dateitypwerte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="f4fe9-156">**Anzeigen von Daten nach: Nachricht:**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="f4fe9-157">**Date**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-157">**Date**</span></span>
  - <span data-ttu-id="f4fe9-158">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-158">**Recipient address**</span></span>
  - <span data-ttu-id="f4fe9-159">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-159">**Sender address**</span></span>
  - <span data-ttu-id="f4fe9-160">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-160">**Message ID**</span></span>
  - <span data-ttu-id="f4fe9-161">**Datei**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-161">**File**</span></span>
  - <span data-ttu-id="f4fe9-162">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-162">**Subject**</span></span>

  <span data-ttu-id="f4fe9-163">Wenn Sie auf **"Filter"** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-164">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-165">Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und der zusätzliche **übergebene** Nachrichtenwert.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="f4fe9-166">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f4fe9-167">Defender für Office 365-Bericht zum Nachrichtenstatus</span><span class="sxs-lookup"><span data-stu-id="f4fe9-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f4fe9-168">Der **ATP-Nachrichtendispositionsbericht** zeigt Ihnen die Aktionen, die für E-Mail-Nachrichten ausgeführt wurden, die als schädliche Inhalte erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="f4fe9-169">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und wählen Sie Defender für Office 365 **Nachrichtendisposition** aus.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-169">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="f4fe9-170">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="f4fe9-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Defender für Office 365 Nachrichtendispositions-Widget im Berichtsdashboard](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f4fe9-172">Die Informationen in diesem Bericht sind auch im [Defender for Office 365-Dateitypenbericht](#defender-for-office-365-file-types-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f4fe9-173">Berichtsansicht für den Bericht "Defender für Office 365 Nachrichtendisposition"</span><span class="sxs-lookup"><span data-stu-id="f4fe9-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f4fe9-174">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-174">The following views are available:</span></span>

- <span data-ttu-id="f4fe9-175">**Anzeigen von Daten nach: Meldung:** Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f4fe9-176">**Zugriff blockieren**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-176">**Block access**</span></span>
  - <span data-ttu-id="f4fe9-177">**Ersetzte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-177">**Messages replaced**</span></span>
  - <span data-ttu-id="f4fe9-178">**Überwachte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-178">**Messages monitored**</span></span>
  - <span data-ttu-id="f4fe9-179">**Ersetzt durch dynamische E-Mail-Zustellung:** Weitere Informationen finden Sie unter ["Dynamische Zustellung in Richtlinien für sichere Anlagen".](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Nachrichtenansicht im Bericht "Defender für Office 365"-Dateitypen](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="f4fe9-181">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-182">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-183">Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und der zusätzliche **übergebene** Nachrichtenwert.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="f4fe9-184">**Anzeigen von Daten nach: Datei:** Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f4fe9-185">**Bösartige Excel Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="f4fe9-186">**Bösartige Flash-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="f4fe9-187">**Schädliche PDF-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="f4fe9-188">**Schädliche PowerPoint Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="f4fe9-189">**Bösartige URLs**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="f4fe9-190">**Bösartige Word-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="f4fe9-191">**Schädliche ausführbare Anlagen**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="f4fe9-192">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-192">**Others**</span></span>

  <span data-ttu-id="f4fe9-193">Wenn Sie mit dem Mauszeiger über einen bestimmten Tag (Datenpunkt) zeigen, sehen Sie die Aufschlüsselung der Arten von schädlichen Dateien, die von [sicheren Anlagen](safe-attachments.md) und [dem Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Dateiansicht im Bericht "Defender für Office 365"-Dateitypen](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="f4fe9-195">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-196">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-197">Die gleichen Dateitypwerte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f4fe9-198">Detailtabellenansicht für den Bericht "Defender für Office 365 Nachrichtendisposition"</span><span class="sxs-lookup"><span data-stu-id="f4fe9-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f4fe9-199">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, bietet der Bericht eine Nahezu-Echtzeitansicht aller Klicks, die innerhalb der Organisation während der letzten 10 Tage stattfinden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="f4fe9-200">Die angezeigten Informationen hängen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f4fe9-201">**Anzeigen von Daten nach: Nachricht:**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="f4fe9-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-202">**Date**</span></span>
  - <span data-ttu-id="f4fe9-203">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-203">**Recipient address**</span></span>
  - <span data-ttu-id="f4fe9-204">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-204">**Sender address**</span></span>
  - <span data-ttu-id="f4fe9-205">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-205">**Message ID**</span></span>
  - <span data-ttu-id="f4fe9-206">**Datei**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-206">**File**</span></span>
  - <span data-ttu-id="f4fe9-207">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-207">**Subject**</span></span>

  <span data-ttu-id="f4fe9-208">Wenn Sie auf **"Filter"** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-209">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-210">Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und der zusätzliche **übergebene** Nachrichtenwert.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="f4fe9-211">**Anzeigen von Daten nach: Datei:**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-211">**View data by: File**:</span></span>

  - <span data-ttu-id="f4fe9-212">**Date**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-212">**Date**</span></span>
  - <span data-ttu-id="f4fe9-213">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-213">**Recipient address**</span></span>
  - <span data-ttu-id="f4fe9-214">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-214">**Sender address**</span></span>
  - <span data-ttu-id="f4fe9-215">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-215">**Message ID**</span></span>
  - <span data-ttu-id="f4fe9-216">**Datei**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-216">**File**</span></span>

  <span data-ttu-id="f4fe9-217">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-218">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-219">Die gleichen Dateitypwerte, die im Diagramm sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="f4fe9-220">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f4fe9-221">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-221">Mail latency report</span></span>

<span data-ttu-id="f4fe9-222">Der **E-Mail-Latenzbericht** zeigt Ihnen eine aggregierte Ansicht der E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f4fe9-223">Die E-Mail-Zustellungszeiten im Dienst werden von einer Reihe von Faktoren beeinflusst, und die absolute Zustellzeit in Sekunden ist häufig kein guter Indikator für Erfolg oder Problem.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="f4fe9-224">Eine langsame Zustellungszeit an einem Tag kann als durchschnittliche Zustellzeit an einem anderen Tag betrachtet werden oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="f4fe9-225">Der **E-Mail-Latenzbericht** versucht, die Nachrichtenübermittlung basierend auf statistischen Daten über die beobachteten Zustellzeiten anderer Nachrichten zu qualifizieren:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="f4fe9-226">**50. Quantil:** Dies ist die Mitte für die Nachrichtenübermittlungszeiten.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="f4fe9-227">Sie können diesen Wert als durchschnittliche Lieferzeit betrachten.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="f4fe9-228">**90. Perzentil:** Dies weist auf eine hohe Latenz für die Nachrichtenübermittlung hin.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="f4fe9-229">Nur 10 % der Nachrichten dauerten länger als dieser Wert für die Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="f4fe9-230">**99. Perzentil:** Gibt die höchste Latenz für die Nachrichtenübermittlung an.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="f4fe9-231">Clientseitige und Netzwerklatenz sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="f4fe9-232">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie unter **E-Mail-Latenzbericht** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-232">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Mail latency report**.</span></span> <span data-ttu-id="f4fe9-233">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="f4fe9-233">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![E-Mail-Latenzberichts-Widget im Berichtsdashboard](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="f4fe9-235">Berichtsansicht für den E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="f4fe9-236">Wenn Sie den Bericht öffnen, ist standardmäßig die **50. Quantilsregisterkarte** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="f4fe9-237">Standardmäßig enthält diese Ansicht ein Diagramm, das mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="f4fe9-238">**Datum:** Die letzten 7 Tage</span><span class="sxs-lookup"><span data-stu-id="f4fe9-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="f4fe9-239">**Nachrichtenansicht:**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-239">**Message View**:</span></span>
  - <span data-ttu-id="f4fe9-240">Detonierte Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f4fe9-240">Detonated messages</span></span>

<span data-ttu-id="f4fe9-241">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f4fe9-242">**E-Mail-Zustellungslatenz**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="f4fe9-243">**Detonationslatenz**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-243">**Detonation latency**</span></span>

<span data-ttu-id="f4fe9-244">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, sehen Sie eine Aufschlüsselung der Latenz in jeder Kategorie.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![E-Mail-Latenzbericht](../../media/mail-latency-report.png)

<span data-ttu-id="f4fe9-246">Wenn Sie in der Berichtsansicht auf **"Filtern"** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f4fe9-247">Alle Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f4fe9-247">All messages</span></span>
- <span data-ttu-id="f4fe9-248">Nachrichten, die Anlagen oder URLs enthalten</span><span class="sxs-lookup"><span data-stu-id="f4fe9-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="f4fe9-249">Wenn Sie auf die Registerkarte **"90. Quantils"** oder **"99. Quantilen"** klicken, werden die gleichen Standardfilter aus der **50. Perzentilansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="f4fe9-250">Detailtabellenansicht für den E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="f4fe9-251">Die folgenden Informationen werden in der Detailtabellenansicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="f4fe9-252">**Date**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-252">**Date**</span></span>
- <span data-ttu-id="f4fe9-253">**Perzentile**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-253">**Percentiles**</span></span>
- <span data-ttu-id="f4fe9-254">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-254">**Message count**</span></span>
- <span data-ttu-id="f4fe9-255">**Gesamtlatenz**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-255">**Overall latency**</span></span>

![Details zum E-Mail-Latenzbericht](../../media/mail-latency-report-details.png)

<span data-ttu-id="f4fe9-257">Oben sehen Sie, dass am 14. November die durchschnittliche Latenz für alle zugestellten und detonierten Nachrichten **108,033** Sekunden betrug.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="f4fe9-258">Die Detailtabelle enthält die gleichen Informationen auf jeder Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f4fe9-259">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-259">Threat protection status report</span></span>

<span data-ttu-id="f4fe9-260">Der **Bedrohungsschutz-Statusbericht** ist eine einzelne Ansicht, die Informationen zu schädlichen Inhalten und schädlichen E-Mails zusammenführt, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) und Microsoft Defender für Office 365 erkannt und blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f4fe9-261">Weitere Informationen finden Sie unter [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="f4fe9-262">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-262">URL threat protection report</span></span>

<span data-ttu-id="f4fe9-263">Der **Bericht zum URL-Bedrohungsschutz** enthält Zusammenfassungen und Trendansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks als Teil [von sicheren Links](safe-links.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="f4fe9-264">In diesem Bericht werden keine Klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links die Option **"Benutzerklicks nicht nachverfolgen"** ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="f4fe9-265">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie auf Details unter **URL-Schutzbericht** **anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-265">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **URL protection report**.</span></span> <span data-ttu-id="f4fe9-266">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="f4fe9-266">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![URL-Schutzberichts-Widget im Berichtsdashboard](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f4fe9-268">Dies ist ein *Schutztrendbericht,* d. h. Daten stellen Trends in einem größeren Dataset dar.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="f4fe9-269">Daher sind die Daten in der Aggregatansicht hier nicht in Echtzeit verfügbar, die Daten in der Detailtabellenansicht sind jedoch so, dass eine geringfügige Abweichung zwischen den beiden Ansichten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="f4fe9-270">Berichtsansicht für den URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="f4fe9-271">Der **URL-Bedrohungsschutzbericht** enthält zwei aggregierte Ansichten, die alle vier Stunden aktualisiert werden und Daten für die letzten 90 Tage anzeigen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="f4fe9-272">Aktion zum Schutz von **URL-Klicks:** Zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klicks an:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="f4fe9-273">**Blockiert** (der Benutzer konnte nicht zur URL navigieren)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="f4fe9-274">**Blockiert und durchgeklickt** (der Benutzer hat sich entschieden, weiter zur URL zu navigieren)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-274">**Blocked and clicked through** (the user has chosen to continue navigating to the URL)</span></span>
  - <span data-ttu-id="f4fe9-275">**Während des Scans durchgeklickt** (der Benutzer hat auf den Link geklickt, bevor der Scan abgeschlossen wurde)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-275">**Clicked through during scan** (the user has clicked on the link before the scan was complete)</span></span>

  <span data-ttu-id="f4fe9-276">Ein Klick gibt an, dass der Benutzer über die Blockierungsseite zur schädlichen Website geklickt hat (Administratoren können das Durchklicken in Richtlinien für sichere Links deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="f4fe9-277">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-278">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-279">Die verfügbaren Klickschutzaktionen sowie der Wert **"Zulässig"** (der Benutzer konnte zur URL navigieren).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-Klickschutz-Aktionsansicht im URL-Bedrohungsschutzbericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="f4fe9-281">**URL-Klick nach Anwendung:** Zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="f4fe9-282">**E-Mail-Client**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-282">**Email client**</span></span>
  - <span data-ttu-id="f4fe9-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-283">**PowerPoint**</span></span>
  - <span data-ttu-id="f4fe9-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-284">**Word**</span></span>
  - <span data-ttu-id="f4fe9-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-285">**Excel**</span></span>
  - <span data-ttu-id="f4fe9-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-286">**OneNote**</span></span>
  - <span data-ttu-id="f4fe9-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-287">**Visio**</span></span>
  - <span data-ttu-id="f4fe9-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-288">**Teams**</span></span>
  - <span data-ttu-id="f4fe9-289">**Other**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-289">**Other**</span></span>

  <span data-ttu-id="f4fe9-290">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f4fe9-291">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f4fe9-292">Die verfügbaren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="f4fe9-293">Detailtabellenansicht für den URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="f4fe9-294">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, bietet der Bericht eine Nahezu-Echtzeitansicht aller Klicks, die innerhalb der Organisation während der letzten 7 Tage stattfinden, mit den folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="f4fe9-295">**Klickzeit**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-295">**Click time**</span></span>
- <span data-ttu-id="f4fe9-296">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-296">**User**</span></span>
- <span data-ttu-id="f4fe9-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-297">**URL**</span></span>
- <span data-ttu-id="f4fe9-298">**Action**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-298">**Action**</span></span>
- <span data-ttu-id="f4fe9-299">**App**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-299">**App**</span></span>

<span data-ttu-id="f4fe9-300">Wenn Sie in der Detailtabellenansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern und auch nach **Domänen** oder **Empfängern,** die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="f4fe9-301">Der **Domänenfilter** verweist auf die URL-Domäne, die in den Berichtergebnissen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="f4fe9-302">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="f4fe9-303">Weitere anzuzeigende Berichte</span><span class="sxs-lookup"><span data-stu-id="f4fe9-303">Additional reports to view</span></span>

<span data-ttu-id="f4fe9-304">Zusätzlich zu den in diesem Artikel beschriebenen Berichten stehen weitere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="f4fe9-305">Bericht</span><span class="sxs-lookup"><span data-stu-id="f4fe9-305">Report</span></span>|<span data-ttu-id="f4fe9-306">Thema</span><span class="sxs-lookup"><span data-stu-id="f4fe9-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="f4fe9-307">**Explorer** (Microsoft Defender für Office 365 Plan 2) oder **Echtzeiterkennungen** (Microsoft Defender für Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="f4fe9-308">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="f4fe9-309">**E-Mail-Sicherheitsberichte,** z. B. der Bericht "Häufigste Absender und Empfänger", der Spoof-E-Mail-Bericht und der Spamerkennungsbericht.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="f4fe9-310">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="f4fe9-310">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="f4fe9-311">**Nachrichtenflussberichte,** z. B. der Weiterleitungsbericht, der E-Mailflow-Statusbericht und der Bericht "Häufigste Absender und Empfänger".</span><span class="sxs-lookup"><span data-stu-id="f4fe9-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="f4fe9-312">Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="f4fe9-312">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="f4fe9-313">**URL-Ablaufverfolgung für sichere Links** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="f4fe9-314">Die Ausgabe dieses Cmdlets zeigt ihnen die Ergebnisse der Aktionen für sichere Links in den letzten sieben Tagen.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="f4fe9-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="f4fe9-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="f4fe9-316">**E-Mail-Datenverkehrsergebnisse für EOP und Microsoft Defender für Office 365** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="f4fe9-317">Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="f4fe9-318">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="f4fe9-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="f4fe9-319">**E-Mail-Detailberichte für EOP und Defender für Office 365 Erkennungen** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="f4fe9-320">Die Ausgabe dieses Cmdlets enthält Details zu schädlichen Dateien oder URLs, Phishingversuchen, Identitätswechsel und anderen potenziellen Bedrohungen in E-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="f4fe9-321">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="f4fe9-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="f4fe9-322">Welche Berechtigungen sind erforderlich, um den Defender für Office 365 Berichte anzuzeigen?</span><span class="sxs-lookup"><span data-stu-id="f4fe9-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="f4fe9-323">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender-Portal sein:</span><span class="sxs-lookup"><span data-stu-id="f4fe9-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f4fe9-324">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-324">**Organization Management**</span></span>
- <span data-ttu-id="f4fe9-325">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-325">**Security Administrator**</span></span>
- <span data-ttu-id="f4fe9-326">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-326">**Security Reader**</span></span>
- <span data-ttu-id="f4fe9-327">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="f4fe9-327">**Global Reader**</span></span>

<span data-ttu-id="f4fe9-328">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-328">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f4fe9-329">**Hinweis:** Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f4fe9-330">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f4fe9-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f4fe9-331">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="f4fe9-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f4fe9-332">Wenn in Ihrem Defender keine Daten für Office 365-Berichte angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f4fe9-333">In Ihrer Organisation müssen Richtlinien für [sichere Links](set-up-safe-links-policies.md) und Richtlinien für [sichere Anlagen](set-up-safe-attachments-policies.md) definiert sein, damit Defender für Office 365 Schutz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f4fe9-333">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="f4fe9-334">Siehe auch [Antispam- und Antischadsoftwareschutz.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f4fe9-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f4fe9-335">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f4fe9-335">Related topics</span></span>

[<span data-ttu-id="f4fe9-336">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="f4fe9-336">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f4fe9-337">Rollenberechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f4fe9-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
