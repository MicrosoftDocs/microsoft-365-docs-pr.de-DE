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
description: Erfahren Sie, wie Sie den Threat Explorer und den Echtzeiterkennungsbericht verwenden, um Bedrohungen im Security & Compliance Center zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406480"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="69b16-103">Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="69b16-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="69b16-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="69b16-104">**Applies to**</span></span>
- [<span data-ttu-id="69b16-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="69b16-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="69b16-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69b16-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Sicherheitsrisiken-Explorer](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="69b16-108">[Der Bedrohungs-Explorer](threat-explorer.md) (und der Bericht über Echtzeiterkennungen) ist ein leistungsfähiges, nahezu echtzeitnahes Tool, mit dem Sicherheitsteams Bedrohungen im Security & Compliance Center untersuchen und darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="69b16-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="69b16-109">Explorer (und der Bericht über Echtzeiterkennungen) zeigt Informationen zu mutmaßlicher Schadsoftware und Phishing in E-Mails und Dateien in Office 365 sowie andere Sicherheitsbedrohungen und Risiken für Ihre Organisation an.</span><span class="sxs-lookup"><span data-stu-id="69b16-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="69b16-110">Wenn Sie [Über Microsoft Defender für Office 365](office-365-atp.md) Plan 2 verfügen, haben Sie Explorer.</span><span class="sxs-lookup"><span data-stu-id="69b16-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="69b16-111">Wenn Sie über Microsoft Defender für Office 365 Plan 1 verfügen, verfügen Sie über Echtzeiterkennungen.</span><span class="sxs-lookup"><span data-stu-id="69b16-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="69b16-112">Wenn Sie Explorer (oder den Bericht über Echtzeiterkennungen) zum ersten Mal öffnen, zeigt die Standardansicht E-Mail-Schadsoftwareerkennungen für die letzten 7 Tage an.</span><span class="sxs-lookup"><span data-stu-id="69b16-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="69b16-113">Dieser Bericht kann auch Microsoft Defender für Office 365-Erkennungen anzeigen, z. B. bösartige URLs, die von sicheren Links erkannt [werden,](atp-safe-links.md)und schädliche Dateien, die von sicheren [Anlagen erkannt werden.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="69b16-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="69b16-114">Dieser Bericht kann so geändert werden, dass Daten für die letzten 30 Tage angezeigt werden (mit einem kostenpflichtigen Microsoft Defender for Office 365 P2-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="69b16-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="69b16-115">Testabonnements enthalten nur Daten für die letzten sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="69b16-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="69b16-116">Abonnement</span><span class="sxs-lookup"><span data-stu-id="69b16-116">Subscription</span></span>|<span data-ttu-id="69b16-117">Dienstprogramm</span><span class="sxs-lookup"><span data-stu-id="69b16-117">Utility</span></span>|<span data-ttu-id="69b16-118">Tage der Daten</span><span class="sxs-lookup"><span data-stu-id="69b16-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="69b16-119">Microsoft Defender für Office 365 P1-Testversion</span><span class="sxs-lookup"><span data-stu-id="69b16-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="69b16-120">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="69b16-120">Real-time detections</span></span>|<span data-ttu-id="69b16-121">7 </span><span class="sxs-lookup"><span data-stu-id="69b16-121">7</span></span>|
|<span data-ttu-id="69b16-122">Microsoft Defender für Office 365 P1 kostenpflichtig</span><span class="sxs-lookup"><span data-stu-id="69b16-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="69b16-123">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="69b16-123">Real-time detections</span></span>|<span data-ttu-id="69b16-124">30</span><span class="sxs-lookup"><span data-stu-id="69b16-124">30</span></span>|
|<span data-ttu-id="69b16-125">Microsoft Defender für Office 365 P1 kostenpflichtige Tests Defender für Office 365 P2-Testversion</span><span class="sxs-lookup"><span data-stu-id="69b16-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="69b16-126">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="69b16-126">Threat Explorer</span></span>|<span data-ttu-id="69b16-127">7 </span><span class="sxs-lookup"><span data-stu-id="69b16-127">7</span></span>|
|<span data-ttu-id="69b16-128">Microsoft Defender für Office 365 P2-Testversion</span><span class="sxs-lookup"><span data-stu-id="69b16-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="69b16-129">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="69b16-129">Threat Explorer</span></span>|<span data-ttu-id="69b16-130">7 </span><span class="sxs-lookup"><span data-stu-id="69b16-130">7</span></span>|
|<span data-ttu-id="69b16-131">Microsoft Defender für Office 365 P2 kostenpflichtig</span><span class="sxs-lookup"><span data-stu-id="69b16-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="69b16-132">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="69b16-132">Threat Explorer</span></span>|<span data-ttu-id="69b16-133">30</span><span class="sxs-lookup"><span data-stu-id="69b16-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="69b16-134">Wir werden in Kürze das Datenaufbewahrungs- und Suchlimit von Explorer (und Echtzeiterkennungen) für Test-Mandanten von 7 auf 30 Tage erweitern.</span><span class="sxs-lookup"><span data-stu-id="69b16-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="69b16-135">Diese Änderung wird im Rahmen des Roadmapelements Nr. 70544 nachverfolgt und befindet sich derzeit in einer Roll-out-Phase.</span><span class="sxs-lookup"><span data-stu-id="69b16-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="69b16-136">Verwenden **Sie** das Menü Ansicht, um zu ändern, welche Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69b16-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="69b16-137">Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69b16-137">Tooltips help you determine which view to use.</span></span>

![Menü "Bedrohungs-Explorer-Ansicht"](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="69b16-139">Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um weitere Analysen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="69b16-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="69b16-140">Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die im Explorer verfügbar sind (oder Echtzeiterkennungen).</span><span class="sxs-lookup"><span data-stu-id="69b16-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="69b16-141">E-Mail > Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="69b16-141">Email > Malware</span></span>

<span data-ttu-id="69b16-142">Um diesen Bericht anzeigen zu können, wählen Sie im Explorer (oder In-Echtzeit-Erkennungen) Die Option **E-Mail-Schadsoftware** \>  \> **anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="69b16-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="69b16-143">Diese Ansicht zeigt Informationen zu E-Mail-Nachrichten, die als Schadsoftware identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="69b16-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Anzeigen von Daten zu E-Mails, die als Schadsoftware identifiziert wurden](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="69b16-145">Klicken **Sie auf Absender,** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69b16-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="69b16-146">Verwenden Sie diese Liste, um Daten nach Absender, Empfängern, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und mehr anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="69b16-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="69b16-147">Wenn Sie beispielsweise sehen möchten, welche Aktionen für erkannte E-Mail-Nachrichten ergriffen wurden, wählen **Sie** in der Liste Schutzstatus aus.</span><span class="sxs-lookup"><span data-stu-id="69b16-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="69b16-148">Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche Aktualisieren, um diesen Filter auf Ihren Bericht anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="69b16-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Optionen für den Bedrohungsschutzstatus für Den Bedrohungs-Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="69b16-150">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="69b16-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="69b16-151">Wenn Sie ein Element in der Liste auswählen, wird ein Fly-Out-Bereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="69b16-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Bedrohungs-Explorer mit geöffneten Flyouts](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="69b16-153">E-Mail > Phish</span><span class="sxs-lookup"><span data-stu-id="69b16-153">Email > Phish</span></span>

<span data-ttu-id="69b16-154">Wählen Sie zum Anzeigen dieses Berichts im Explorer (oder in Echtzeiterkennungen) **Die** Option E-Mail-Phish \>  \> **anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="69b16-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="69b16-155">Diese Ansicht zeigt E-Mail-Nachrichten, die als Phishingversuche identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="69b16-155">This view shows email messages identified as phishing attempts.</span></span>

![Anzeigen von Daten zu E-Mails, die als Phishingversuche identifiziert wurden](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="69b16-157">Klicken **Sie auf Absender,** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69b16-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="69b16-158">Verwenden Sie diese Liste zum Anzeigen von Daten nach Absender, Empfängern, Absenderdomäne, Absender-IP, URL-Domäne, klicken Sie auf Urteil und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69b16-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="69b16-159">Wenn Sie beispielsweise sehen möchten, welche Aktionen beim Klicken auf URLs, die als Phishingversuche identifiziert wurden, ergriffen wurden, wählen Sie **in** der Liste Auf Urteil klicken, wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="69b16-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicken Sie für den Phish-Bericht auf Die Diktieroptionen.](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="69b16-161">Unter dem Diagramm können Sie weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und E-Mail-Ursprung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="69b16-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URLs, die in E-Mail-Nachrichten als Phish erkannt werden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="69b16-163">Wenn Sie ein Element in der Liste auswählen, z. B. eine gefundene URL, wird ein Fly-Out-Bereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.</span><span class="sxs-lookup"><span data-stu-id="69b16-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="69b16-165">E>-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="69b16-165">Email > Submissions</span></span>

<span data-ttu-id="69b16-166">Wählen Sie zum Anzeigen dieses Berichts im Explorer (oder in Echtzeiterkennungen) **Die** Option E-Mail-Übermittlungen \>  \> **anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="69b16-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="69b16-167">Diese Ansicht zeigt E-Mails, die Benutzer als Junk- und nicht Junk- oder Phishing-E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="69b16-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Von Benutzern gemeldete E-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="69b16-169">Klicken **Sie auf Absender,** um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69b16-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="69b16-170">Verwenden Sie diese Liste, um Informationen nach Absender, Empfängern, Berichtstyp (der Bestimmung des Benutzers, dass es sich bei der E-Mail um Junk, nicht Junk oder Phishing) und vieles mehr handeln soll.</span><span class="sxs-lookup"><span data-stu-id="69b16-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="69b16-171">Wenn Sie z. B. Informationen zu E-Mail-Nachrichten anzeigen möchten, die als Phishingversuche gemeldet wurden, klicken Sie auf Absenderberichtstyp, Wählen Sie  \>  **Phish** aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="69b16-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish selected for Report Type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="69b16-173">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, IP-Adresse des Absenders, Benutzer, der die Nachricht als Junk, nicht Junk oder Phishing gemeldet hat, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69b16-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Nachrichten, die als Phishingversuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="69b16-175">Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69b16-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="69b16-176">E> Alle E-Mails</span><span class="sxs-lookup"><span data-stu-id="69b16-176">Email > All email</span></span>

<span data-ttu-id="69b16-177">Um diesen Bericht anzeigen zu können, wählen Sie im Explorer **E-Mail** \> **alle** \> **E-Mails anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="69b16-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="69b16-178">Diese Ansichten zeigen eine all-up-Ansicht von E-Mail-Aktivitäten, einschließlich E-Mails, die aufgrund von Phishing oder Schadsoftware als schädlich identifiziert wurden, sowie alle nicht schädlichen E-Mails (normale E-Mails, Spam und Massen-E-Mails).</span><span class="sxs-lookup"><span data-stu-id="69b16-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="69b16-179">Wenn Sie einen Fehler erhalten, der **Zu** viele Daten zum Anzeigen liest, fügen Sie einen Filter hinzu, und verengt gegebenenfalls den angezeigten Datumsbereich.</span><span class="sxs-lookup"><span data-stu-id="69b16-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="69b16-180">Wenn Sie einen Filter anwenden möchten, wählen Sie **Absender** aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="69b16-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="69b16-181">In unserem Beispiel haben wir die **Erkennungstechnologie** als Filter verwendet (es stehen mehrere Optionen zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="69b16-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="69b16-182">Anzeigen von Informationen nach Absender, Absenderdomäne, Empfängern, Betreff, Anlagendateiname, Schadsoftwarefamilie, Schutzstatus (Aktionen, die von Den Bedrohungsschutzfeatures und -richtlinien in Office 365 ergriffen wurden), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69b16-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Anzeigen von Daten zu erkannten E-Mails durch Erkennungstechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="69b16-184">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, Empfänger, Absender, Status und so weiter.</span><span class="sxs-lookup"><span data-stu-id="69b16-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="69b16-185">Inhalt > Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="69b16-185">Content > Malware</span></span>

<span data-ttu-id="69b16-186">Um diesen Bericht anzuzeigen, wählen Sie im Explorer (oder In-Echtzeit-Erkennungen) Die Option **Inhalt Schadsoftware** \>  \> **anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="69b16-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="69b16-187">Diese Ansicht zeigt Dateien, die von [Microsoft Defender für Office 365 in SharePoint Online, OneDrive for Business](atp-for-spo-odb-and-teams.md)und Microsoft Teams als schädlich identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="69b16-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="69b16-188">Anzeigen von Informationen nach Schadsoftwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Arbeitsauslastung (OneDrive, SharePoint oder Teams).</span><span class="sxs-lookup"><span data-stu-id="69b16-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Anzeigen von Daten über erkannte Schadsoftware](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="69b16-190">Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Dateien an, z. B. Anlagendateiname, Arbeitsauslastung, Dateigröße, Personen, die die Datei zuletzt geändert haben, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69b16-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="69b16-191">Klick-und-Filter-Funktionen</span><span class="sxs-lookup"><span data-stu-id="69b16-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="69b16-192">Mit Explorer (und Echtzeiterkennungen) können Sie einen Filter mit einem Klick anwenden.</span><span class="sxs-lookup"><span data-stu-id="69b16-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="69b16-193">Klicken Sie in der Legende auf ein Element, und dieses Element wird zu einem Filter für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="69b16-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="69b16-194">Angenommen, wir sehen uns die Schadsoftwareansicht im Explorer an:</span><span class="sxs-lookup"><span data-stu-id="69b16-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Wechseln sie zu \> Bedrohungsverwaltungs-Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="69b16-196">Wenn Sie in diesem Diagramm auf **ATP-Detonation** klicken, wird eine Ansicht wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="69b16-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer gefiltert, um nur Defender for Office 365 Detonation Ergebnisse anzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="69b16-198">In dieser Ansicht sehen wir uns nun Daten für Dateien an, die von sicheren Anlagen [detoniert wurden.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="69b16-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="69b16-199">Unterhalb des Diagramms sehen wir Details zu bestimmten E-Mail-Nachrichten mit Anlagen, die von sicheren Anlagen erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="69b16-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Spezifische Details zu E-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="69b16-201">Durch Auswählen eines oder mehrerer Elemente wird das Menü **Aktionen** aktiviert, das verschiedene Auswahlmöglichkeiten für die ausgewählten Elemente bietet.</span><span class="sxs-lookup"><span data-stu-id="69b16-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Durch Auswählen eines Elements wird das Menü Aktionen aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="69b16-203">Die Möglichkeit, mit einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen bei der Untersuchung von Bedrohungen viel Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="69b16-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="69b16-204">Abfragen und Filter</span><span class="sxs-lookup"><span data-stu-id="69b16-204">Queries and filters</span></span>

<span data-ttu-id="69b16-205">Der Explorer (sowie der Bericht über Echtzeiterkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie details anzeigen können, z. B. Top-Zielbenutzer, Top-Malwarefamilien, Erkennungstechnologie und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69b16-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="69b16-206">Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Untersuchen von Daten.</span><span class="sxs-lookup"><span data-stu-id="69b16-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69b16-207">Verwenden Sie keine Platzhalterzeichen, z. B. sternchen oder Fragezeichen, in der Abfrageleiste für Explorer (oder Echtzeiterkennungen).</span><span class="sxs-lookup"><span data-stu-id="69b16-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="69b16-208">Wenn Sie im  Feld Betreff nach E-Mail-Nachrichten suchen, führt Explorer (oder Echtzeiterkennungen) einen teilweisen Abgleich durch und liefert Ergebnisse, die einer Platzhaltersuche ähneln.</span><span class="sxs-lookup"><span data-stu-id="69b16-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
