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
description: Erfahren Sie, wie Sie den Bedrohungs-Explorer und den Bericht über Echtzeiterkennungen verwenden, um Bedrohungen im Microsoft 365 Defender-Portal zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c79cc717a2dbe345627f99830590c674fa02f09
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929635"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="a0aa4-103">Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="a0aa4-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a0aa4-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="a0aa4-104">**Applies to**</span></span>
- [<span data-ttu-id="a0aa4-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="a0aa4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a0aa4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0aa4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Sicherheitsrisiken-Explorer](../../media/explorer.png)

<span data-ttu-id="a0aa4-108">[Der Bedrohungs-Explorer](threat-explorer.md) (und der Bericht über Echtzeiterkennungen) ist ein leistungsstarkes, nahezu in Echtzeit verfügbares Tool, mit dem Sicherheitsteams Bedrohungen im Microsoft 365 Defender-Portal untersuchen und darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="a0aa4-109">Explorer (und der Bericht über Echtzeiterkennungen) zeigt Informationen zu verdächtiger Schadsoftware und Phishing in E-Mails und Dateien in Office 365 sowie andere Sicherheitsbedrohungen und Risiken für Ihre Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="a0aa4-110">Wenn Sie [über Microsoft Defender für Office 365](defender-for-office-365.md) Plan 2 verfügen, verfügen Sie über Explorer.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="a0aa4-111">Wenn Sie Über Microsoft Defender für Office 365 Plan 1 verfügen, haben Sie Echtzeiterkennungen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="a0aa4-112">Wenn Sie den Explorer (oder den Bericht über Echtzeiterkennungen) zum ersten Mal öffnen, zeigt die Standardansicht E-Mail-Schadsoftwareerkennungen für die letzten 7 Tage an.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="a0aa4-113">Dieser Bericht kann auch Microsoft Defender für Office 365 Erkennungen anzeigen, z. B. bösartige URLs, die von [sicheren Links](safe-links.md)erkannt werden, und schädliche Dateien, die von [sicheren Anlagen](safe-attachments.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="a0aa4-114">Dieser Bericht kann so geändert werden, dass Daten für die letzten 30 Tage angezeigt werden (mit einem kostenpflichtigen Microsoft Defender für Office 365 P2-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="a0aa4-115">Testabonnements enthalten nur Daten für die letzten sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="a0aa4-116">Abonnement</span><span class="sxs-lookup"><span data-stu-id="a0aa4-116">Subscription</span></span>|<span data-ttu-id="a0aa4-117">Dienstprogramm</span><span class="sxs-lookup"><span data-stu-id="a0aa4-117">Utility</span></span>|<span data-ttu-id="a0aa4-118">Datentage</span><span class="sxs-lookup"><span data-stu-id="a0aa4-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="a0aa4-119">Testversion von Microsoft Defender für Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="a0aa4-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="a0aa4-120">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="a0aa4-120">Real-time detections</span></span>|<span data-ttu-id="a0aa4-121">7 </span><span class="sxs-lookup"><span data-stu-id="a0aa4-121">7</span></span>|
|<span data-ttu-id="a0aa4-122">Microsoft Defender für Office 365 P1 bezahlt</span><span class="sxs-lookup"><span data-stu-id="a0aa4-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="a0aa4-123">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="a0aa4-123">Real-time detections</span></span>|<span data-ttu-id="a0aa4-124">30</span><span class="sxs-lookup"><span data-stu-id="a0aa4-124">30</span></span>|
|<span data-ttu-id="a0aa4-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span><span class="sxs-lookup"><span data-stu-id="a0aa4-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="a0aa4-126">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="a0aa4-126">Threat Explorer</span></span>|<span data-ttu-id="a0aa4-127">7 </span><span class="sxs-lookup"><span data-stu-id="a0aa4-127">7</span></span>|
|<span data-ttu-id="a0aa4-128">Testversion von Microsoft Defender für Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="a0aa4-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="a0aa4-129">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="a0aa4-129">Threat Explorer</span></span>|<span data-ttu-id="a0aa4-130">7 </span><span class="sxs-lookup"><span data-stu-id="a0aa4-130">7</span></span>|
|<span data-ttu-id="a0aa4-131">Microsoft Defender für Office 365 P2, bezahlt</span><span class="sxs-lookup"><span data-stu-id="a0aa4-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="a0aa4-132">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="a0aa4-132">Threat Explorer</span></span>|<span data-ttu-id="a0aa4-133">30</span><span class="sxs-lookup"><span data-stu-id="a0aa4-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="a0aa4-134">Wir werden in Kürze die Datenaufbewahrungs- und Suchgrenze von Explorer (und Echtzeiterkennungen) für Testmandanten von 7 auf 30 Tage erweitern.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="a0aa4-135">Diese Änderung wird als Teil des Roadmap-Elements Nr. 70544 nachverfolgt und befindet sich derzeit in einer Rolloutphase.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="a0aa4-136">Verwenden Sie das Menü **"Ansicht",** um zu ändern, welche Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="a0aa4-137">Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-137">Tooltips help you determine which view to use.</span></span>

![Menü "Ansicht des Bedrohungs-Explorers"](../../media/all-email.png)

<span data-ttu-id="a0aa4-139">Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um weitere Analysen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="a0aa4-140">Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die im Explorer verfügbar sind (oder Echtzeiterkennungen).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="a0aa4-141">E-Mail-> Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="a0aa4-141">Email > Malware</span></span>

<span data-ttu-id="a0aa4-142">Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) die Option \> **"E-Mail-Schadsoftware** \> anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="a0aa4-143">In dieser Ansicht werden Informationen zu E-Mail-Nachrichten angezeigt, die als schadsoftware enthalten identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Anzeigen von Daten zu E-Mails, die als Schadsoftware identifiziert wurden](../../media/detection-technology.png)

<span data-ttu-id="a0aa4-145">Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a0aa4-146">Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und mehr anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="a0aa4-147">Wenn Sie beispielsweise sehen möchten, welche Aktionen für erkannte E-Mail-Nachrichten ausgeführt wurden, wählen Sie den **Schutzstatus** in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="a0aa4-148">Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren", um diesen Filter auf Ihren Bericht anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Optionen für den Bedrohungsschutzstatus für den Bedrohungs-Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="a0aa4-150">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="a0aa4-151">Wenn Sie ein Element in der Liste auswählen, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Bedrohungs-Explorer mit geöffneter Flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="a0aa4-153">E-Mail-> Phishing</span><span class="sxs-lookup"><span data-stu-id="a0aa4-153">Email > Phish</span></span>

<span data-ttu-id="a0aa4-154">Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) \> **E-Mail-Phishing** anzeigen \> aus.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="a0aa4-155">In dieser Ansicht werden E-Mail-Nachrichten angezeigt, die als Phishingversuche identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-155">This view shows email messages identified as phishing attempts.</span></span>

![Anzeigen von Daten zu E-Mails, die als Phishingversuche identifiziert wurden](../../media/phish.png)

<span data-ttu-id="a0aa4-157">Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a0aa4-158">Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Absender-IP, URL-Domäne, Klickbewertung und mehr anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="a0aa4-159">Um beispielsweise zu sehen, welche Aktionen ausgeführt wurden, wenn Benutzer auf URLs geklickt haben, die als Phishingversuche identifiziert wurden, wählen Sie in der Liste **auf "Bewertung klicken",** wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="a0aa4-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicken Sie auf die Bewertungsoptionen für den Phishingbericht.](../../media/click-verdict.png)

<span data-ttu-id="a0aa4-161">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und E-Mail-Ursprung an.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URLs, die in E-Mail-Nachrichten als Phishing erkannt wurden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="a0aa4-163">Wenn Sie ein Element in der Liste auswählen, z. B. eine url, die erkannt wurde, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="a0aa4-165">E-Mail->-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="a0aa4-165">Email > Submissions</span></span>

<span data-ttu-id="a0aa4-166">Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) die Option \> **"E-Mail-Übermittlungen** \> anzeigen" **aus.**</span><span class="sxs-lookup"><span data-stu-id="a0aa4-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="a0aa4-167">Diese Ansicht zeigt E-Mails, die Benutzer als Junk-, nicht Junk- oder Phishing-E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Von Benutzern gemeldete E-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="a0aa4-169">Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a0aa4-170">Verwenden Sie diese Liste, um Informationen nach Absender, Empfängern, Berichtstyp (die Entscheidung des Benutzers, dass die E-Mail Junk war, nicht Junk oder Phishing) und mehr anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="a0aa4-171">Wenn Sie z. B. Informationen zu E-Mail-Nachrichten anzeigen möchten, die als Phishingversuche gemeldet wurden, klicken Sie auf  \> **"Absenderbericht",** wählen Sie **"Phishing"** aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="a0aa4-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Für den Berichtstypfilter ausgewählter Phishing-Wert](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="a0aa4-173">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, DIE IP-Adresse des Absenders, der Benutzer, der die Nachricht als Junk, nicht Junk oder Phishing gemeldet hat, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Nachrichten, die als Phishingversuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="a0aa4-175">Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="a0aa4-176">E-Mail > Alle E-Mails</span><span class="sxs-lookup"><span data-stu-id="a0aa4-176">Email > All email</span></span>

<span data-ttu-id="a0aa4-177">Um diesen Bericht anzuzeigen,  wählen Sie im Explorer \> **"Alle E-Mail anzeigen"** \> aus.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="a0aa4-178">Diese Ansichten zeigen eine Gesamtansicht der E-Mail-Aktivitäten, einschließlich E-Mails, die aufgrund von Phishing oder Schadsoftware als bösartig erkannt wurden, sowie alle nicht schädlichen E-Mails (normale E-Mails, Spam und Massen-E-Mails).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="a0aa4-179">Wenn ein Fehler angezeigt wird, der **zu viele Daten anzeigt,** fügen Sie einen Filter hinzu, und schränken Sie ggf. den angezeigten Datumsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="a0aa4-180">Um einen Filter anzuwenden, wählen Sie **"Absender"** aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="a0aa4-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="a0aa4-181">In unserem Beispiel haben wir **die Erkennungstechnologie** als Filter verwendet (es stehen mehrere Optionen zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="a0aa4-182">Anzeigen von Informationen nach Absender, Domäne des Absenders, Empfänger, Betreff, Dateiname der Anlage, Schadsoftwarefamilie, Schutzstatus (Aktionen, die von Ihren Bedrohungsschutzfeatures und -richtlinien in Office 365 ausgeführt werden), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Anzeigen von Daten zu erkannten E-Mails durch Erkennungstechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="a0aa4-184">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, Empfänger, Absender, Status usw.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="a0aa4-185">Inhalt > Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="a0aa4-185">Content > Malware</span></span>

<span data-ttu-id="a0aa4-186">Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) \> **inhaltsbezogene** \> **Schadsoftware** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="a0aa4-187">In dieser Ansicht werden Dateien angezeigt, die von [Microsoft Defender für Office 365 in SharePoint Online, OneDrive for Business und Microsoft Teams](mdo-for-spo-odb-and-teams.md)als bösartig erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="a0aa4-188">Anzeigen von Informationen nach Schadsoftwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Workload (OneDrive, SharePoint oder Teams).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Anzeigen von Daten zu erkannter Schadsoftware](../../media/malware-family.png)

<span data-ttu-id="a0aa4-190">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Dateien an, z. B. Anlagendateiname, Arbeitsauslastung, Dateigröße, wer die Datei zuletzt geändert hat und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="a0aa4-191">Klick-und-Filter-Funktionen</span><span class="sxs-lookup"><span data-stu-id="a0aa4-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="a0aa4-192">Mit Explorer (und Echtzeiterkennungen) können Sie einen Filter in einem Klick anwenden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="a0aa4-193">Klicken Sie in der Legende auf ein Element, und dieses Element wird zu einem Filter für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="a0aa4-194">Nehmen wir beispielsweise an, dass wir die Schadsoftwareansicht im Explorer betrachten:</span><span class="sxs-lookup"><span data-stu-id="a0aa4-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Wechseln sie zum Explorer für die \> Bedrohungsverwaltung](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="a0aa4-196">Durch Klicken auf **die ATP-Detonation** in diesem Diagramm wird eine Ansicht wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a0aa4-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer gefiltert, um nur Defender für Office 365 Detonation-Ergebnisse anzuzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="a0aa4-198">In dieser Ansicht betrachten wir jetzt Daten für Dateien, die durch [sichere Anlagen](safe-attachments.md)detoniert wurden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="a0aa4-199">Unterhalb des Diagramms sehen wir Details zu bestimmten E-Mail-Nachrichten mit Anlagen, die von sicheren Anlagen erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Spezifische Details zu E-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="a0aa4-201">Wenn Sie ein oder mehrere Elemente auswählen, wird das Menü **"Aktionen"** aktiviert, das mehrere Auswahlmöglichkeiten für die ausgewählten Elemente bietet.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Wenn Sie ein Element auswählen, wird das Menü "Aktionen" aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="a0aa4-203">Die Möglichkeit, in einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen viel Zeit bei der Untersuchung von Bedrohungen sparen.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="a0aa4-204">Abfragen und Filter</span><span class="sxs-lookup"><span data-stu-id="a0aa4-204">Queries and filters</span></span>

<span data-ttu-id="a0aa4-205">Der Explorer (sowie der Bericht über Echtzeiterkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie details anzeigen können, z. B. benutzerorientierte Top-Benutzer, top Schadsoftwarefamilien, Erkennungstechnologie und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="a0aa4-206">Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Erkunden von Daten.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0aa4-207">Verwenden Sie keine Platzhalterzeichen, z. B. ein Sternchen oder ein Fragezeichen, in der Abfrageleiste für Explorer (oder Echtzeiterkennungen).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="a0aa4-208">Wenn Sie im **Feld Betreff** nach E-Mail-Nachrichten suchen, führt Explorer (oder Echtzeiterkennungen) einen teilweisen Abgleich durch und liefert Ergebnisse, die einer Platzhaltersuche ähneln.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
