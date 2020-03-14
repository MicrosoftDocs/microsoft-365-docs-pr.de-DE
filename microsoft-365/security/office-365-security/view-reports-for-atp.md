---
title: Anzeigen von Berichten für Office 365 Advanced Threat Protection, Schadsoftware-Berichte, Phishing-Berichte, kompromittierte Konten, URL-Schutzstatus, Threat Reporting, melden von Bedrohungen
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 02/07/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Suchen und Verwenden von Berichten für Office 365 Advanced Threat Protection im Security &amp; Compliance Center.
ms.openlocfilehash: 1531a70439ae1c093ee472923696895eda0bc644
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634083"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="6da81-103">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6da81-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="6da81-104">Wenn Ihre Organisation über [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) verfügt und Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-atp-reports)verfügen, können Sie mehrere ATP-Berichte im &amp; Security Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="6da81-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6da81-105">(Wechseln Sie zum **Dashboard** **Berichte** \> .)</span><span class="sxs-lookup"><span data-stu-id="6da81-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Das Security &amp; Compliance Center-Dashboard hilft Ihnen, zu sehen, wo Advanced Threat Protection funktioniert.](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="6da81-107">Zu den ATP-Berichten zählen folgende:</span><span class="sxs-lookup"><span data-stu-id="6da81-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="6da81-108">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="6da81-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="6da81-109">ATP-Dateitypenbericht</span><span class="sxs-lookup"><span data-stu-id="6da81-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="6da81-110">ATP-Bericht zum Nachrichtenstatus</span><span class="sxs-lookup"><span data-stu-id="6da81-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="6da81-111">entweder [Echtzeiterkennung oder Explorer](threat-explorer.md) (je nachdem, ob Sie Office 365 ATP-Plan 1 oder 2 haben)</span><span class="sxs-lookup"><span data-stu-id="6da81-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="6da81-112">... [und vieles mehr](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="6da81-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="6da81-113">Lesen Sie diesen Artikel, um eine Übersicht über ATP-Berichte und deren Verwendung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6da81-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="6da81-114">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="6da81-114">Threat Protection Status report</span></span>

<span data-ttu-id="6da81-115">Der **Status Bericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails zusammengefasst werden, die durch [Exchange Online Schutz](exchange-online-protection-overview.md) (EoP) und [Office 365 ATP](office-365-atp.md)erkannt und blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="6da81-116">Dieser Bericht eignet sich zum Anzeigen von Erkennungen im Laufe der Zeit (bis zu 90 Tage) und ermöglicht es Sicherheitsadministratoren, Trends zu identifizieren oder zu bestimmen, ob Richtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6da81-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="6da81-117">Der Bericht enthält eine aggregierte Anzahl von eindeutigen e-Mail-Nachrichten mit bösartigen Inhalten wie Dateien oder Websiteadressen (URLs), die durch das Anti-Malware-Modul, die [Zero-Hour-automatische Bereinigung (AUTOPURGE)](zero-hour-auto-purge.md)und ATP-Features wie [ATP-sichere Links](atp-safe-links.md), [ATP-sichere Anlagen](atp-safe-attachments.md)und [ATP-Anti-Phishing-Funktionen](atp-anti-phishing.md)blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

<span data-ttu-id="6da81-118">Filter und Aufschlüsselung der Informationen ermöglichen eine granularere Kategorisierung der Informationen in diesem Bericht.</span><span class="sxs-lookup"><span data-stu-id="6da81-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="6da81-119">Insbesondere gibt es ein Menü "Aufteilen von" für *e-Mails > Phishing* -und *e-Mail-> Malware-Ansichten*.</span><span class="sxs-lookup"><span data-stu-id="6da81-119">Specifically, there is a 'break down by' menu included for *Email > Phish* and *Email > Malware views*.</span></span> <span data-ttu-id="6da81-120">Die Daten werden in folgendem aufgeschlüsselt:</span><span class="sxs-lookup"><span data-stu-id="6da81-120">It will break down the data into:</span></span>

| |  |
|---------|---------|
|<span data-ttu-id="6da81-121">Nach Erkennungstyp</span><span class="sxs-lookup"><span data-stu-id="6da81-121">By detection type</span></span>    | <span data-ttu-id="6da81-122">Welche Richtlinien haben dazu beigetragen, diese Bedrohungen zu erfassen?</span><span class="sxs-lookup"><span data-stu-id="6da81-122">What policy helped catch these threats?</span></span>         |
|<span data-ttu-id="6da81-123">Nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="6da81-123">By detection technology</span></span>     | <span data-ttu-id="6da81-124">Welche zugrunde liegende Microsoft-Technologie hat die Bedrohung erfasst?</span><span class="sxs-lookup"><span data-stu-id="6da81-124">What underlying Microsoft technology caught the threat?</span></span>        |
|<span data-ttu-id="6da81-125">Nach Zustellungsstatus</span><span class="sxs-lookup"><span data-stu-id="6da81-125">By delivery status</span></span>     | <span data-ttu-id="6da81-126">Was geschah mit den e-Mail-Nachrichten, die als Bedrohungen erkannt wurden?</span><span class="sxs-lookup"><span data-stu-id="6da81-126">What happened to the email messages detected as threats?</span></span>         |
| | |

> [!TIP]
> <span data-ttu-id="6da81-127">Sowohl die e-Mail-> Phishing | Schadsoftware-Ansichten weisen eine granulare Aufschlüsselung der angezeigten Erkennungstechnologien auf, wobei Kategorien wie *ATP-generierte dateireputation*, *Datei Detonation*, *URL-Detonation*, *Antispoofing: DMARC-Fehler*hilfreich ist, um genau zu ermitteln, welche Funktion Ihre Organisation veranlasst hat, Bedrohungen einzufangen.</span><span class="sxs-lookup"><span data-stu-id="6da81-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Dropdown mit dem Status Bericht zum Bedrohungsschutz mit "aufschlüsseln nach".](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="6da81-129">Diese Ansichten bieten Ihnen die Möglichkeit, über eine Schaltfläche per Mausklick (in e-Mail > Phishing, e-Mail-> Schadsoftware und Inhalte > Malware Ansichten) zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6da81-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="6da81-130">Die aggregierten Daten, die auf Ihren Computer exportiert werden, können in Excel geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="6da81-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Diese Grafik zeigt den Export als Option im Menü für die Malware-Ansicht, rechts zwischen Create Schedule und Request Report.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="6da81-132">In den Ansichten Übersicht und e-Mails werden Informationen innerhalb von Stunden nach der Verarbeitung und nicht in 24 Stunden angezeigt (Demand Re.</span><span class="sxs-lookup"><span data-stu-id="6da81-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="6da81-133">erhöhte Geschwindigkeiten hier war ein deutliches Signal)!</span><span class="sxs-lookup"><span data-stu-id="6da81-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="6da81-134">Ein Status Bericht über den Bedrohungsschutz steht Kunden zur Verfügung, die entweder [Office 365 ATP](office-365-atp.md) oder [Exchange Online Protection](exchange-online-protection-eop.md) (EoP) haben; die Informationen, die im Threat Protection-Status Bericht für ATP-Kunden angezeigt werden, enthalten jedoch wahrscheinlich unterschiedliche Daten, als EoP-Kunden möglicherweise sehen.</span><span class="sxs-lookup"><span data-stu-id="6da81-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="6da81-135">Der Threat Protection-Status Bericht für ATP-Kunden enthält beispielsweise Informationen zu [schädlichen Dateien, die in SharePoint Online, OneDrive oder Microsoft Teams erkannt](atp-for-spo-odb-and-teams.md)wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="6da81-136">Solche Informationen gelten nur für ATP, sodass Kunden, die über EoP, aber nicht ATP verfügen, diese Details nicht in Ihrem Threat Protection-Status Bericht sehen.</span><span class="sxs-lookup"><span data-stu-id="6da81-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="6da81-137">Wechseln Sie zum Anzeigen des Statusberichts für den Bedrohungsschutz im [ &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **Threat Protection Status**.</span><span class="sxs-lookup"><span data-stu-id="6da81-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Status Bericht über den ATP-Bedrohungsschutz](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="6da81-139">Wenn Sie einen detaillierten Status für einen Tag erhalten möchten, zeigen Sie mit der Maus auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="6da81-139">To get detailed status for a day, hover over the graph.</span></span>
  
![Status Daten für den ATP-Bedrohungsschutz für einen Tag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="6da81-141">Standardmäßig zeigt der Status Bericht zum Bedrohungsschutz Daten für die letzten sieben Tage an.</span><span class="sxs-lookup"><span data-stu-id="6da81-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="6da81-142">Sie können jedoch **Filter** auswählen und den Datumsbereich ändern, um Daten für bis zu 90 Tage anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6da81-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="6da81-143">(Wenn Sie ein Testabonnement verwenden, sind die Daten möglicherweise auf 30 Tage eingeschränkt.)</span><span class="sxs-lookup"><span data-stu-id="6da81-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Status Filter für den ATP-Bedrohungsschutz](../../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="6da81-145">Sie können auch das Menü " **Daten anzeigen nach** " verwenden, um zu ändern, welche Informationen im Bericht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6da81-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Anzeigen von Optionen für den Status Bericht für den ATP-Bedrohungsschutz](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="6da81-147">Status Bericht über den URL-Schutz</span><span class="sxs-lookup"><span data-stu-id="6da81-147">URL Protection Status report</span></span>

<span data-ttu-id="6da81-148">In diesem Bericht werden gesammelte Daten und erkannte Bedrohungen pro Klick erstellt (während die meisten anderen e-Mail-Bedrohungs bezogenen Berichte pro Nachrichtendaten sind).</span><span class="sxs-lookup"><span data-stu-id="6da81-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="6da81-149">Dieser Bericht dient zum Anzeigen von Bedrohungen, die durch Hyperlinks in e-Mail-Nachrichten und Dokumenten pro Klick entstehen.</span><span class="sxs-lookup"><span data-stu-id="6da81-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="6da81-150">Es gibt zwei Ansichten:</span><span class="sxs-lookup"><span data-stu-id="6da81-150">There are two views:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="6da81-151">Aktion "URL-Klick Schutz"</span><span class="sxs-lookup"><span data-stu-id="6da81-151">URL click protection action</span></span>   | <span data-ttu-id="6da81-152">Sehen Sie sich die Anzahl der blockierten URLs an, die mit einem Mausklick durch einen Benutzer außer Kraft gesetzt, aber mit einem Mausklick durch einen Benutzer überschrieben und zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="6da81-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>        |
|<span data-ttu-id="6da81-153">URL-Klick nach Anwendung</span><span class="sxs-lookup"><span data-stu-id="6da81-153">URL click by application</span></span>     | <span data-ttu-id="6da81-154">Sehen Sie sich die Anwendung an, auf die die URL geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6da81-154">See the application from which the URL was clicked.</span></span>        |
|  |  |

<span data-ttu-id="6da81-155">In der Detailtabelle können Sie weitere Informationen zu Klick Zeiten und Benutzerinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6da81-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="6da81-156">Denken Sie daran, dass der Status Bericht über den URL-Schutz den Schutz vor dem Feature für ATP-sichere Links anzeigt, sodass nur Kunden, die ATP-sichere Links aktiviert haben, Daten in diesem Bericht anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="6da81-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="6da81-157">Hierbei handelt es sich um einen *Schutz Trendbericht*, was bedeutet, dass Datentrends in einem größeren DataSet darstellen.</span><span class="sxs-lookup"><span data-stu-id="6da81-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="6da81-158">Die Berichterstellung steht hier in Echtzeit nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6da81-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="6da81-159">Für die Echt Zeit URL klicken Sie auf Daten, und verwenden Sie weiterhin die URL-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="6da81-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="6da81-160">ATP-Dateitypenbericht</span><span class="sxs-lookup"><span data-stu-id="6da81-160">ATP File Types report</span></span>

<span data-ttu-id="6da81-161">Der Bericht " **ATP-Dateitypen** " zeigt Ihnen den Typ der Dateien, die von [ATP-Safe-Anlagen](atp-safe-attachments.md)als bösartig erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-161">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="6da81-162">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **ATP-Dateitypen**.</span><span class="sxs-lookup"><span data-stu-id="6da81-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP-Dateitypenbericht](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="6da81-164">Wenn Sie den Mauszeiger über einen bestimmten Tag bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [ATP-sichere Anlagen](atp-safe-attachments.md) und [Anti &amp; -Spam-Schutz vor Schadsoftware in Office 365](anti-spam-and-anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-164">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP-Dateitypen-Berichtsdaten für einen Tag](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="6da81-166">ATP-Bericht zum Nachrichtenstatus</span><span class="sxs-lookup"><span data-stu-id="6da81-166">ATP Message Disposition report</span></span>

<span data-ttu-id="6da81-167">Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-167">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="6da81-168">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Berichte** \> **-Dashboard** \> **ATP-Nachrichten Disposition**.</span><span class="sxs-lookup"><span data-stu-id="6da81-168">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Bericht zur ATP-Nachrichten Disposition](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="6da81-170">Wenn Sie mit dem Mauszeiger auf einen Balken im Diagramm zeigen, können Sie sehen, welche Aktionen für erkannte e-Mails an diesem Tag ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6da81-170">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![ATP-Nachrichten Dispositions-Berichtsdaten für einen Tag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="6da81-172">Zusätzliche Berichte zur Anzeige</span><span class="sxs-lookup"><span data-stu-id="6da81-172">Additional reports to view</span></span>

<span data-ttu-id="6da81-173">Zusätzlich zu den in diesem Artikel beschriebenen ATP-Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="6da81-173">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="6da81-174">Bericht (e)</span><span class="sxs-lookup"><span data-stu-id="6da81-174">Report(s)</span></span>  |<span data-ttu-id="6da81-175">Details</span><span class="sxs-lookup"><span data-stu-id="6da81-175">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="6da81-176">**Explorer** oder **Echtzeiterkennung** (Office 365 ATP-Plan 2-Kunden haben Explorer; Office 365 ATP-Plan 1 haben Kunden Echt Zeit Erkennungen.)</span><span class="sxs-lookup"><span data-stu-id="6da81-176">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="6da81-177">Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)</span><span class="sxs-lookup"><span data-stu-id="6da81-177">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="6da81-178">**E-Mail-Sicherheitsberichte**wie ein Bericht über die wichtigsten Absender und Empfänger, ein spoof-e-Mail-Bericht und ein Spam Erkennungs Bericht.</span><span class="sxs-lookup"><span data-stu-id="6da81-178">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="6da81-179">Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6da81-179">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="6da81-180">**URL-Ablaufverfolgung für ATP-sichere Links** (Dies ist ein Bericht, den Sie mithilfe von PowerShell generieren.) In diesem Bericht werden die Ergebnisse der Aktionen für ATP-sichere Links in den letzten sieben (7) Tagen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6da81-180">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="6da81-181">Get-UrlTrace-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="6da81-181">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="6da81-182">**EoP und ATP-Ergebnisse** (Dies ist ein benutzerdefinierter Bericht, den Sie mithilfe von PowerShell generieren).</span><span class="sxs-lookup"><span data-stu-id="6da81-182">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="6da81-183">Dieser Bericht enthält Informationen wie Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="6da81-183">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="6da81-184">Get-MailTrafficATPReport-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="6da81-184">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="6da81-185">**EoP und ATP-Erkennungen** (Dies ist ein benutzerdefinierter Bericht, den Sie mithilfe von PowerShell generieren).</span><span class="sxs-lookup"><span data-stu-id="6da81-185">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="6da81-186">Dieser Bericht enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="6da81-186">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="6da81-187">Get-MailDetailATPReport-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="6da81-187">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="6da81-188">Welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="6da81-188">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="6da81-189">Damit Sie die in diesem Artikel beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.</span><span class="sxs-lookup"><span data-stu-id="6da81-189">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="6da81-190">Für das Security &amp; Compliance Center müssen Sie eine der folgenden Rollen zugewiesen haben:</span><span class="sxs-lookup"><span data-stu-id="6da81-190">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="6da81-191">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6da81-191">Organization Management</span></span>
    - <span data-ttu-id="6da81-192">Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="6da81-192">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="6da81-193">Sicherheits Operator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="6da81-193">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="6da81-194">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="6da81-194">Security Reader</span></span>

- <span data-ttu-id="6da81-195">Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="6da81-195">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="6da81-196">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6da81-196">Organization Management</span></span>
    - <span data-ttu-id="6da81-197">Organisationsverwaltung mit Leserechten</span><span class="sxs-lookup"><span data-stu-id="6da81-197">View-only Organization Management</span></span>
    - <span data-ttu-id="6da81-198">Rolle „Empfänger mit Leserechten“</span><span class="sxs-lookup"><span data-stu-id="6da81-198">View-Only Recipients role</span></span>
    - <span data-ttu-id="6da81-199">Verwaltung der Richtlinientreue</span><span class="sxs-lookup"><span data-stu-id="6da81-199">Compliance Management</span></span>

<span data-ttu-id="6da81-200">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="6da81-200">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="6da81-201">Berechtigungen im Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6da81-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="6da81-202">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6da81-202">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="6da81-203">Was geschieht, wenn die Berichte keine Daten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="6da81-203">What if the reports aren't showing data?</span></span>

<span data-ttu-id="6da81-204">Wenn Sie keine Daten in ihren ATP-Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="6da81-204">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="6da81-205">In Ihrer Organisation müssen Richtlinien für [ATP-sichere Links](set-up-atp-safe-links-policies.md) und [ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit ATP-Schutz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6da81-205">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="6da81-206">Weitere Informationen finden Sie unter [Anti-Spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="6da81-206">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6da81-207">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6da81-207">Related topics</span></span>

[<span data-ttu-id="6da81-208">Berichte und Einblicke im Office 365 &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6da81-208">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="6da81-209">Erstellen eines Zeitplans für einen Bericht im &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6da81-209">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="6da81-210">Einrichten und Herunterladen eines benutzerdefinierten Berichts im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6da81-210">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="6da81-211">Rollen Berechtigungen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6da81-211">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
  

