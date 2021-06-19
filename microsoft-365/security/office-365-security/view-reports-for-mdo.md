---
title: Microsoft Defender für Office 365-Berichte anzeigen
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
description: Administratoren können erfahren, wie Sie defender für Office 365 Berichte finden und verwenden, die im Microsoft 365 Defender-Portal verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9279614571c123ad92f1684f86175b410c6c5c
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022841"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="b8a6d-103">Anzeigen von Defender für Office 365 Berichte im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="b8a6d-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b8a6d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-104">**Applies to**</span></span>
- [<span data-ttu-id="b8a6d-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="b8a6d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b8a6d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8a6d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b8a6d-107">Microsoft Defender für Office 365 Organisationen (z. B. Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-Ons) enthalten eine Vielzahl von sicherheitsrelevanten Berichten.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="b8a6d-108">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **Zusammenarbeit E-Mail & Zusammenarbeitsberichte** wechseln.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b8a6d-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="b8a6d-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Seite "E-Mail & Zusammenarbeitsberichte" im Microsoft 365 Defender Portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="b8a6d-111">E-Mail-Sicherheitsberichte, für die Defender nicht für Office 365 erforderlich ist, werden in [den E-Mail-Sicherheitsberichten im Microsoft 365 Defender Portal](view-email-security-reports.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="b8a6d-112">Berichte, die sich auf den Nachrichtenfluss beziehen, befinden sich jetzt im Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="b8a6d-113">Weitere Informationen zu diesen Berichten finden Sie unter [Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="b8a6d-114">Safe Anlagendateitypenbericht</span><span class="sxs-lookup"><span data-stu-id="b8a6d-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="b8a6d-115">Der **Bericht Safe Dateitypen "Anlagen"** wird schließlich entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="b8a6d-116">Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="b8a6d-117">Safe Dispositionsbericht über Anlagennachrichten</span><span class="sxs-lookup"><span data-stu-id="b8a6d-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="b8a6d-118">Der **Dispositionsbericht Safe Attachments-Nachricht** wird schließlich entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="b8a6d-119">Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b8a6d-120">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="b8a6d-120">Mail latency report</span></span>

<span data-ttu-id="b8a6d-121">Der **E-Mail-Latenzbericht** zeigt Ihnen eine aggregierte Ansicht der E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b8a6d-122">Die E-Mail-Zustellungszeiten im Dienst werden von einer Reihe von Faktoren beeinflusst, und die absolute Zustellzeit in Sekunden ist häufig kein guter Indikator für Erfolg oder Problem.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="b8a6d-123">Eine langsame Zustellungszeit an einem Tag kann als durchschnittliche Zustellzeit an einem anderen Tag betrachtet werden oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="b8a6d-124">Dadurch wird versucht, die Nachrichtenübermittlung basierend auf statistischen Daten über die beobachteten Zustellungszeiten anderer Nachrichten zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="b8a6d-125">Clientseitige und Netzwerklatenz sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="b8a6d-126">Um den Bericht anzuzeigen, öffnen Sie das [portal Microsoft 365 Defender](https://security.microsoft.com), wechseln Sie zu **Berichte** \> **E-Mail & Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte.**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b8a6d-127">Suchen Sie auf der Seite **"E-Mail-& Zusammenarbeitsberichte"** den **Bericht "E-Mail-Latenz",** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="b8a6d-128">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="b8a6d-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![E-Mail-Latenzbericht-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/mail-latency-report-widget.png)

<span data-ttu-id="b8a6d-130">Auf der Seite **"E-Mail-Latenzbericht"** sind die folgenden Registerkarten auf der Seite **"E-Mail-Latenzbericht"** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="b8a6d-131">**50. Quantil:** Dies ist die Mitte für die Nachrichtenübermittlungszeiten.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="b8a6d-132">Sie können diesen Wert als durchschnittliche Lieferzeit betrachten.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="b8a6d-133">Diese Registerkarte ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-133">This tab is selected by default.</span></span>
- <span data-ttu-id="b8a6d-134">**90. Perzentil:** Dies weist auf eine hohe Latenz für die Nachrichtenübermittlung hin.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="b8a6d-135">Nur 10 % der Nachrichten dauerten länger als dieser Wert für die Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="b8a6d-136">**99. Perzentil:** Gibt die höchste Latenz für die Nachrichtenübermittlung an.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="b8a6d-137">Unabhängig von der ausgewählten Registerkarte zeigt das Diagramm Nachrichten in den folgenden Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b8a6d-138">**E-Mail-Zustellungslatenz**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="b8a6d-139">**Detonationen**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-139">**Detonations**</span></span>

<span data-ttu-id="b8a6d-140">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, sehen Sie eine Aufschlüsselung der Latenz in jeder Kategorie.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![50. Perzentilansicht des E-Mail-Latenzberichts](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="b8a6d-142">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Detailtabelle nach den folgenden Werten filtern:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="b8a6d-143">**Datum (UTC):** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b8a6d-144">**Nachrichtenansicht:** Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="b8a6d-145">**Alle Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-145">**All messages**</span></span>
  - <span data-ttu-id="b8a6d-146">**Nachrichten, die Anlagen oder URLs enthalten**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="b8a6d-147">**Detonierte Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-147">**Detonated messages**</span></span>

<span data-ttu-id="b8a6d-148">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b8a6d-149">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b8a6d-150">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-150">**Date (UTC)**</span></span>
- <span data-ttu-id="b8a6d-151">**Perzentile:** **50**, **90** oder **99**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="b8a6d-152">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-152">**Message count**</span></span>
- <span data-ttu-id="b8a6d-153">**Gesamtlatenz**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="b8a6d-154">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="b8a6d-154">Threat protection status report</span></span>

<span data-ttu-id="b8a6d-155">Der **Bedrohungsschutz-Statusbericht** ist eine einzelne Ansicht, die Informationen zu schädlichen Inhalten und schädlichen E-Mails zusammenführt, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) und Microsoft Defender für Office 365 erkannt und blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b8a6d-156">Weitere Informationen finden Sie unter [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="b8a6d-157">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="b8a6d-157">URL threat protection report</span></span>

<span data-ttu-id="b8a6d-158">Der **Bericht zum URL-Bedrohungsschutz** enthält Zusammenfassungen und Trendansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen [Safe Links](safe-links.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="b8a6d-159">In diesem Bericht werden keine Klickdaten von Benutzern angezeigt, bei denen für die angewendete richtlinie für Safe Verknüpfungen die Option **"Benutzerklicks nicht nachverfolgen"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="b8a6d-160">Um den Bericht anzuzeigen, öffnen Sie das [portal Microsoft 365 Defender](https://security.microsoft.com), wechseln Sie zu **Berichte** \> **E-Mail & Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte.**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b8a6d-161">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die **Url-Schutzseite,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="b8a6d-162">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="b8a6d-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![URL-Schutzberichts-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/url-protection-report-widget.png)

<span data-ttu-id="b8a6d-164">Die verfügbaren Ansichten auf der Berichtsseite zum **URL-Bedrohungsschutz** werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a6d-165">Dies ist ein *Schutztrendbericht,* d. h. Daten stellen Trends in einem größeren Dataset dar.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="b8a6d-166">Daher sind die Daten in den Diagrammen hier nicht in Echtzeit verfügbar, aber die Daten in der Detailtabelle sind vorhanden, sodass möglicherweise eine geringfügige Abweichung zwischen den beiden angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="b8a6d-167">Die Diagramme werden alle vier Stunden aktualisiert und enthalten Daten für die letzten 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="b8a6d-168">Anzeigen von Daten nach URL-Klickschutzaktion</span><span class="sxs-lookup"><span data-stu-id="b8a6d-168">View data by URL click protection action</span></span>

![URL-Klickschutz-Aktionsansicht im URL-Bedrohungsschutzbericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="b8a6d-170">Die Aktionsansicht **"Daten nach URL anzeigen" zeigt** die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klicks an:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="b8a6d-171">**Zulässig:** Der Benutzer konnte zur URL navigieren.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="b8a6d-172">**Blockiert:** Der Benutzer wurde am Navigieren zur URL gehindert.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="b8a6d-173">**Blockiert und durchgeklickt:** Der Benutzer hat sich entschieden, weiter zur URL zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="b8a6d-174">**Während des Scans durchgeklickt:** Der Benutzer hat auf den Link geklickt, bevor die Überprüfung abgeschlossen war.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="b8a6d-175">Ein Klick gibt an, dass der Benutzer durch die Blockierungsseite zur schädlichen Website geklickt hat (Administratoren können click through in Safe Links policies deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="b8a6d-176">Wenn Sie auf **Filter** klicken, können Sie den Bericht und die Detailtabelle ändern, indem Sie einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b8a6d-177">**Datum (UTC):** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b8a6d-178">**Erkennung:**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-178">**Detection**:</span></span>
  - <span data-ttu-id="b8a6d-179">**Zulässig**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-179">**Allowed**</span></span>
  - <span data-ttu-id="b8a6d-180">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-180">**Blocked**</span></span>
  - <span data-ttu-id="b8a6d-181">**Blockiert und durchgeklickt**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="b8a6d-182">**Während des Scans durchgeklickt**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="b8a6d-183">**Domänen:** Die in den Berichtergebnissen aufgeführten URL-Domänen.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="b8a6d-184">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-184">**Recipients**</span></span>

<span data-ttu-id="b8a6d-185">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b8a6d-186">Die Detailtabelle unterhalb des Diagramms bietet die folgende Nahezu-Echtzeit-Ansicht aller Klicks, die in der Organisation während der letzten 7 Tage aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="b8a6d-187">**Klickzeit**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-187">**Click time**</span></span>
- <span data-ttu-id="b8a6d-188">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-188">**User**</span></span>
- <span data-ttu-id="b8a6d-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-189">**URL**</span></span>
- <span data-ttu-id="b8a6d-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-190">**Action**</span></span>
- <span data-ttu-id="b8a6d-191">**App**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="b8a6d-192">Anzeigen von Daten nach URL-Klick nach Anwendung</span><span class="sxs-lookup"><span data-stu-id="b8a6d-192">View data by URL click by application</span></span>

![URL-Klick nach Anwendungsansicht im URL-Bedrohungsschutzbericht](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="b8a6d-194">Die **Ansichtsdaten nach URL klicken nach Anwendungsansicht** zeigt die Anzahl der URL-Klicks von Apps an, die Safe Links unterstützen:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="b8a6d-195">**E-Mail-Client**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-195">**Email client**</span></span>
- <span data-ttu-id="b8a6d-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-196">**PowerPoint**</span></span>
- <span data-ttu-id="b8a6d-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-197">**Word**</span></span>
- <span data-ttu-id="b8a6d-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-198">**Excel**</span></span>
- <span data-ttu-id="b8a6d-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-199">**OneNote**</span></span>
- <span data-ttu-id="b8a6d-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-200">**Visio**</span></span>
- <span data-ttu-id="b8a6d-201">**Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-201">**Teams**</span></span>
- <span data-ttu-id="b8a6d-202">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-202">**Others**</span></span>

<span data-ttu-id="b8a6d-203">Wenn Sie auf **Filter** klicken, können Sie den Bericht und die Detailtabelle ändern, indem Sie einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b8a6d-204">**Datum (UTC):** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b8a6d-205">**Erkennung:** Verfügbare Apps aus dem Diagramm.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="b8a6d-206">**Domänen:** Die in den Berichtergebnissen aufgeführten URL-Domänen.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="b8a6d-207">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-207">**Recipients**</span></span>

<span data-ttu-id="b8a6d-208">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b8a6d-209">Die Detailtabelle unterhalb des Diagramms bietet die folgende Nahezu-Echtzeit-Ansicht aller Klicks, die in der Organisation während der letzten 7 Tage aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="b8a6d-210">**Klickzeit**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-210">**Click time**</span></span>
- <span data-ttu-id="b8a6d-211">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-211">**User**</span></span>
- <span data-ttu-id="b8a6d-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-212">**URL**</span></span>
- <span data-ttu-id="b8a6d-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-213">**Action**</span></span>
- <span data-ttu-id="b8a6d-214">**App**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="b8a6d-215">Weitere anzuzeigende Berichte</span><span class="sxs-lookup"><span data-stu-id="b8a6d-215">Additional reports to view</span></span>

<span data-ttu-id="b8a6d-216">Zusätzlich zu den in diesem Artikel beschriebenen Berichten stehen weitere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="b8a6d-217">Bericht</span><span class="sxs-lookup"><span data-stu-id="b8a6d-217">Report</span></span>|<span data-ttu-id="b8a6d-218">Thema</span><span class="sxs-lookup"><span data-stu-id="b8a6d-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="b8a6d-219">**Explorer** (Microsoft Defender für Office 365 Plan 2) oder **Echtzeiterkennungen** (Microsoft Defender für Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="b8a6d-220">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="b8a6d-221">**E-Mail-Sicherheitsberichte,** z. B. der Bericht "Häufigste Absender und Empfänger", der Spoof-E-Mail-Bericht und der Spamerkennungsbericht.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="b8a6d-222">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="b8a6d-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="b8a6d-223">**Nachrichtenflussberichte,** z. B. der Weiterleitungsbericht, der E-Mailflow-Statusbericht und der Bericht "Häufigste Absender und Empfänger".</span><span class="sxs-lookup"><span data-stu-id="b8a6d-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="b8a6d-224">Nachrichtenflussberichte im neuen Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="b8a6d-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="b8a6d-225">**URL-Ablaufverfolgung für Safe Links** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="b8a6d-226">Die Ausgabe dieses Cmdlets zeigt die Ergebnisse der aktionen Safe Links in den letzten sieben Tagen an.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="b8a6d-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="b8a6d-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="b8a6d-228">**E-Mail-Datenverkehrsergebnisse für EOP und Microsoft Defender für Office 365** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="b8a6d-229">Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="b8a6d-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="b8a6d-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="b8a6d-231">**E-Mail-Detailberichte für EOP und Defender für Office 365 Erkennungen** (nur PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="b8a6d-232">Die Ausgabe dieses Cmdlets enthält Details zu schädlichen Dateien oder URLs, Phishingversuchen, Identitätswechsel und anderen potenziellen Bedrohungen in E-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="b8a6d-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="b8a6d-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="b8a6d-234">Welche Berechtigungen sind erforderlich, um den Defender für Office 365 Berichte anzuzeigen?</span><span class="sxs-lookup"><span data-stu-id="b8a6d-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="b8a6d-235">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender Portal sein:</span><span class="sxs-lookup"><span data-stu-id="b8a6d-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="b8a6d-236">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-236">**Organization Management**</span></span>
- <span data-ttu-id="b8a6d-237">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-237">**Security Administrator**</span></span>
- <span data-ttu-id="b8a6d-238">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-238">**Security Reader**</span></span>
- <span data-ttu-id="b8a6d-239">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="b8a6d-239">**Global Reader**</span></span>

<span data-ttu-id="b8a6d-240">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b8a6d-241">**Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b8a6d-242">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b8a6d-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b8a6d-243">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="b8a6d-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b8a6d-244">Wenn in Ihrem Defender keine Daten für Office 365-Berichte angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b8a6d-245">In Ihrer Organisation müssen [Safe Verknüpfungsrichtlinien](set-up-safe-links-policies.md) und [Safe Anlagenrichtlinien](set-up-safe-attachments-policies.md) definiert sein, damit Defender für Office 365 Schutz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b8a6d-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="b8a6d-246">Siehe auch [Antispam- und Antischadsoftwareschutz.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b8a6d-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8a6d-247">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b8a6d-247">Related topics</span></span>

[<span data-ttu-id="b8a6d-248">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="b8a6d-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b8a6d-249">Rollenberechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8a6d-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
