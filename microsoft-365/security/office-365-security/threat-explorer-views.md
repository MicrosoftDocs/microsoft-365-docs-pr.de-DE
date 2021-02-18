---
title: Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie, wie Sie den Bedrohungs-Explorer und den Bericht über Echtzeiterkennungen verwenden, um Bedrohungen im Security & Compliance Center zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290285"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="52183-103">Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="52183-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="52183-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="52183-104">**Applies to**</span></span>
- [<span data-ttu-id="52183-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="52183-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="52183-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52183-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Sicherheitsrisiken-Explorer](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="52183-108">[Der Bedrohungs-Explorer](threat-explorer.md) (und der Bericht über Echtzeiterkennungen) ist ein leistungsstarkes, nahezu echtzeitnahes Tool, mit dem Sicherheitsteams Bedrohungen im Security & Compliance Center untersuchen und darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="52183-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="52183-109">Explorer (und der Bericht über Echtzeiterkennungen) zeigt Informationen zu verdächtiger Schadsoftware und Phishing in E-Mails und Dateien in Office 365 sowie andere Sicherheitsbedrohungen und Risiken für Ihre Organisation an.</span><span class="sxs-lookup"><span data-stu-id="52183-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="52183-110">Wenn Sie [über Microsoft Defender für Office 365](office-365-atp.md) Plan 2 verfügen, verfügen Sie über Explorer.</span><span class="sxs-lookup"><span data-stu-id="52183-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="52183-111">Wenn Sie über Microsoft Defender für Office 365 Plan 1 verfügen, verfügen Sie über Echtzeiterkennungen.</span><span class="sxs-lookup"><span data-stu-id="52183-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="52183-112">Wenn Sie Explorer (oder den Bericht über Echtzeiterkennungen) zum ersten Mal öffnen, werden in der Standardansicht E-Mail-Schadsoftwareerkennungen für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52183-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="52183-113">Dieser Bericht kann auch Microsoft Defender für Office 365-Erkennungen anzeigen, z. B. bösartige URLs, die von sicheren Links erkannt [werden,](atp-safe-links.md)und schädliche Dateien, die von sicheren Anlagen [erkannt werden.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="52183-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="52183-114">Dieser Bericht kann so geändert werden, dass Daten für die letzten 30 Tage angezeigt werden (mit einem kostenpflichtigen Microsoft Defender für Office 365 P2-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="52183-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="52183-115">Testabonnements enthalten nur Daten für die letzten sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="52183-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="52183-116">Abonnement</span><span class="sxs-lookup"><span data-stu-id="52183-116">Subscription</span></span>|<span data-ttu-id="52183-117">Dienstprogramm</span><span class="sxs-lookup"><span data-stu-id="52183-117">Utility</span></span>|<span data-ttu-id="52183-118">Tage der Daten</span><span class="sxs-lookup"><span data-stu-id="52183-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="52183-119">Testversion von Microsoft Defender für Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="52183-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="52183-120">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="52183-120">Real-time detections</span></span>|<span data-ttu-id="52183-121">7 </span><span class="sxs-lookup"><span data-stu-id="52183-121">7</span></span>|
|<span data-ttu-id="52183-122">Microsoft Defender für Office 365 P1 kostenpflichtig</span><span class="sxs-lookup"><span data-stu-id="52183-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="52183-123">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="52183-123">Real-time detections</span></span>|<span data-ttu-id="52183-124">30</span><span class="sxs-lookup"><span data-stu-id="52183-124">30</span></span>|
|<span data-ttu-id="52183-125">Testversion von Microsoft Defender für Office 365 P1 mit kostenpflichtigen Tests für Defender für Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="52183-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="52183-126">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="52183-126">Threat Explorer</span></span>|<span data-ttu-id="52183-127">7 </span><span class="sxs-lookup"><span data-stu-id="52183-127">7</span></span>|
|<span data-ttu-id="52183-128">Testversion von Microsoft Defender für Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="52183-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="52183-129">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="52183-129">Threat Explorer</span></span>|<span data-ttu-id="52183-130">7 </span><span class="sxs-lookup"><span data-stu-id="52183-130">7</span></span>|
|<span data-ttu-id="52183-131">Microsoft Defender für Office 365 P2 kostenpflichtig</span><span class="sxs-lookup"><span data-stu-id="52183-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="52183-132">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="52183-132">Threat Explorer</span></span>|<span data-ttu-id="52183-133">30</span><span class="sxs-lookup"><span data-stu-id="52183-133">30</span></span>|
|

<span data-ttu-id="52183-134">Verwenden Sie das **Menü** "Ansicht", um zu ändern, welche Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="52183-134">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="52183-135">Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52183-135">Tooltips help you determine which view to use.</span></span>

![Menü "Ansicht des Bedrohungs-Explorers"](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="52183-137">Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um weitere Analysen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="52183-137">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="52183-138">Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die im Explorer verfügbar sind (oder Echtzeiterkennungen).</span><span class="sxs-lookup"><span data-stu-id="52183-138">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="52183-139">Schadsoftware > E-Mail</span><span class="sxs-lookup"><span data-stu-id="52183-139">Email > Malware</span></span>

<span data-ttu-id="52183-140">Wählen Sie zum Anzeigen dieses Berichts im Explorer (oder in Echtzeiterkennungen) die Option **"E-Mail-Schadsoftware** \>  \> **anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52183-140">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="52183-141">In dieser Ansicht werden Informationen zu E-Mail-Nachrichten angezeigt, die als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="52183-141">This view shows information about email messages that were identified as containing malware.</span></span>

![Anzeigen von Daten zu E-Mails, die als Schadsoftware identifiziert wurden](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="52183-143">Klicken **Sie auf "Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52183-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="52183-144">In dieser Liste können Sie Daten nach Absender, Empfängern, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und mehr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52183-144">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="52183-145">Um beispielsweise zu sehen, welche Aktionen für erkannte E-Mail-Nachrichten ergriffen wurden, **wählen** Sie in der Liste "Schutzstatus" aus.</span><span class="sxs-lookup"><span data-stu-id="52183-145">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="52183-146">Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren", um diesen Filter auf Ihren Bericht anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="52183-146">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Bedrohungsschutzstatusoptionen für Den Bedrohungs-Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="52183-148">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="52183-148">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="52183-149">Wenn Sie ein Element in der Liste auswählen, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="52183-149">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Bedrohungs-Explorer mit geöffneter Flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="52183-151">Phishing > E-Mail</span><span class="sxs-lookup"><span data-stu-id="52183-151">Email > Phish</span></span>

<span data-ttu-id="52183-152">Um diesen Bericht anzeigen zu können, wählen Sie im Explorer (oder in Echtzeit Erkennungen) die Option "E-Mail-Phishing  \>  \> **anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52183-152">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="52183-153">In dieser Ansicht werden E-Mail-Nachrichten angezeigt, die als Phishingversuche identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="52183-153">This view shows email messages identified as phishing attempts.</span></span>

![Anzeigen von Daten zu E-Mails, die als Phishingversuche identifiziert wurden](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="52183-155">Klicken **Sie auf "Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52183-155">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="52183-156">Verwenden Sie diese Liste zum Anzeigen von Daten nach Absender, Empfängern, Absenderdomäne, Absender-IP, URL-Domäne, Klicken auf "Verdingung" und mehr.</span><span class="sxs-lookup"><span data-stu-id="52183-156">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="52183-157">Um z. B. zu sehen, welche Aktionen beim Klicken auf URLs, die als Phishingversuche identifiziert wurden, ergriffen wurden, wählen Sie in der Liste **"Click-Verdict"** aus, wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="52183-157">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Click verdict options for the Phish report](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="52183-159">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und E-Mail-Ursprung an.</span><span class="sxs-lookup"><span data-stu-id="52183-159">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URLs, die in E-Mail-Nachrichten als Phishing erkannt wurden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="52183-161">Wenn Sie ein Element in der Liste auswählen, z. B. eine url, die erkannt wurde, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="52183-161">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="52183-163">E->-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="52183-163">Email > Submissions</span></span>

<span data-ttu-id="52183-164">Wählen Sie zum Anzeigen dieses Berichts im Explorer (oder in Echtzeiterkennungen) die Option "E-Mail-Übermittlungen  \>  \> **anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52183-164">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="52183-165">Diese Ansicht zeigt E-Mails, die Benutzer als Junk-E-Mail, nicht als Junk- oder Phishing-E-Mail gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="52183-165">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Von Benutzern gemeldete E-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="52183-167">Klicken **Sie auf "Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52183-167">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="52183-168">Verwenden Sie diese Liste, um Informationen nach Absender, Empfängern, Berichtstyp (die Bestimmung des Benutzers, dass es sich bei der E-Mail um Junk- oder Phishing-E-Mails handeln soll) und vieles mehr anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="52183-168">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="52183-169">Wenn Sie beispielsweise Informationen zu E-Mail-Nachrichten anzeigen möchten, die als Phishingversuche gemeldet wurden, klicken Sie auf **"Absenderbericht",** wählen \>  **"Phishing"** aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="52183-169">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish selected for Report Type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="52183-171">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, die IP-Adresse des Absenders, den Benutzer, der die Nachricht als Junk, nicht Junk oder Phishing gemeldet hat, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="52183-171">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Nachrichten, die als Phishingversuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="52183-173">Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="52183-173">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="52183-174">E> Alle E-Mails</span><span class="sxs-lookup"><span data-stu-id="52183-174">Email > All email</span></span>

<span data-ttu-id="52183-175">Wählen Sie zum Anzeigen dieses Berichts im Explorer **"Alle** E-Mails \>  \> **anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52183-175">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="52183-176">Diese Ansichten zeigen eine all-up-Ansicht der E-Mail-Aktivitäten, einschließlich E-Mails, die aufgrund von Phishing oder Schadsoftware als bösartig identifiziert wurden, sowie alle nicht schädlichen E-Mails (normale E-Mails, Spam und Massen-E-Mails).</span><span class="sxs-lookup"><span data-stu-id="52183-176">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="52183-177">Wenn eine Fehlermeldung angezeigt wird, die zu viele Daten zum Anzeigen **liest,** fügen Sie einen Filter hinzu, und enengnen Sie bei Bedarf den angezeigten Datumsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="52183-177">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="52183-178">Wählen Sie zum Anwenden eines Filters **"Absender"** aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="52183-178">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="52183-179">In unserem Beispiel haben wir die **Erkennungstechnologie** als Filter verwendet (es stehen mehrere Optionen zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="52183-179">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="52183-180">Informationen nach Absender, Absenderdomäne, Empfänger, Betreff, Anlagendateiname, Schadsoftwarefamilie, Schutzstatus (Aktionen, die von Ihren Bedrohungsschutzfeatures und -richtlinien in Office 365 ergriffen wurden), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52183-180">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Anzeigen von Daten zu erkannten E-Mails nach Erkennungstechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="52183-182">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, Empfänger, Absender, Status und so weiter.</span><span class="sxs-lookup"><span data-stu-id="52183-182">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="52183-183">Inhalt > Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="52183-183">Content > Malware</span></span>

<span data-ttu-id="52183-184">Um diesen Bericht anzuzeigen, wählen Sie im Explorer (oder In-Time-Erkennungen) die Option **"Schadsoftware** \>  \> **anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52183-184">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="52183-185">Diese Ansicht zeigt Dateien, die von [Microsoft Defender für Office 365 in SharePoint Online, OneDrive for Business](atp-for-spo-odb-and-teams.md)und Microsoft Teams als bösartig identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="52183-185">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="52183-186">Anzeigen von Informationen nach Schadsoftwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Arbeitsauslastung (OneDrive, SharePoint oder Teams).</span><span class="sxs-lookup"><span data-stu-id="52183-186">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Anzeigen von Daten über erkannte Schadsoftware](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="52183-188">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Dateien an, z. B. den Dateinamen der Anlage, die Arbeitsauslastung, die Dateigröße, den Benutzer, der die Datei zuletzt geändert hat, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="52183-188">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="52183-189">Klick-und-Filter-Funktionen</span><span class="sxs-lookup"><span data-stu-id="52183-189">Click-to-filter capabilities</span></span>

<span data-ttu-id="52183-190">Mit Explorer (und Echtzeiterkennungen) können Sie einen Filter mit einem Klick anwenden.</span><span class="sxs-lookup"><span data-stu-id="52183-190">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="52183-191">Klicken Sie auf ein Element in der Legende, und dieses Element wird zu einem Filter für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="52183-191">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="52183-192">Angenommen, wir betrachten die Ansicht "Schadsoftware" im Explorer:</span><span class="sxs-lookup"><span data-stu-id="52183-192">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Wechseln sie zum Explorer für die \> Bedrohungsverwaltung](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="52183-194">Wenn Sie in diesem Diagramm auf die **ATP-Detonation** klicken, wird eine Ansicht wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="52183-194">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer gefiltert, um nur Defender für Office 365-Detonationsergebnisse anzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="52183-196">In dieser Ansicht betrachten wir nun Daten für Dateien, die durch sichere Anlagen [gedetont wurden.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="52183-196">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="52183-197">Unterhalb des Diagramms sehen wir Details zu bestimmten E-Mail-Nachrichten mit Anlagen, die von sicheren Anlagen erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="52183-197">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Spezifische Details zu E-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="52183-199">Durch Auswählen eines oder mehrerer Elemente wird das **Menü** "Aktionen" aktiviert, das verschiedene Auswahlmöglichkeiten für die ausgewählten Elemente bietet.</span><span class="sxs-lookup"><span data-stu-id="52183-199">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Durch Auswählen eines Elements wird das Menü "Aktionen" aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="52183-201">Die Möglichkeit, mit einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen bei der Untersuchung von Bedrohungen viel Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="52183-201">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="52183-202">Abfragen und Filter</span><span class="sxs-lookup"><span data-stu-id="52183-202">Queries and filters</span></span>

<span data-ttu-id="52183-203">Der Explorer (sowie der Bericht über Echtzeiterkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie Details anzeigen können, z. B. die benutzersten Benutzer, die am stärksten betroffenen Schadsoftwarefamilien, die Erkennungstechnologie und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="52183-203">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="52183-204">Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Untersuchen von Daten.</span><span class="sxs-lookup"><span data-stu-id="52183-204">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52183-205">Verwenden Sie in der Abfrageleiste für Explorer (oder Echtzeiterkennungen) keine Platzhalterzeichen wie Sternchen oder Fragezeichen.</span><span class="sxs-lookup"><span data-stu-id="52183-205">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="52183-206">Wenn Sie im  Feld "Betreff" nach E-Mail-Nachrichten suchen, führt Explorer (oder Echtzeiterkennungen) einen teilweisen Abgleich durch und liefert Ergebnisse ähnlich wie bei einer Platzhaltersuche.</span><span class="sxs-lookup"><span data-stu-id="52183-206">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
