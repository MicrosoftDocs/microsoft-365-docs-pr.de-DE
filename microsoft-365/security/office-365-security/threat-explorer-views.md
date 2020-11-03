---
title: Ansichten im Threat Explorer und Echt Zeit Erkennungen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: In diesem Artikel erfahren Sie, wie Sie Threat Explorer und den Bericht über Echt Zeit Erkennungen verwenden, um Bedrohungen im Security Compliance Center zu untersuchen und auf diese zu reagieren &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 83fa2d89c74b5ec1e2de7e65457313f20bbf2681
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844320"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="36e97-103">Ansichten im Threat Explorer und Echt Zeit Erkennungen</span><span class="sxs-lookup"><span data-stu-id="36e97-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Sicherheitsrisiken-Explorer](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="36e97-105">[Threat Explorer](threat-explorer.md) (und der Bericht über Echt Zeit Erkennungen) ist ein leistungsfähiges, near-Echt Zeit Tool, um Sicherheitsteams beim untersuchen und reagieren auf Bedrohungen im Security Compliance Center zu unterstützen &amp; .</span><span class="sxs-lookup"><span data-stu-id="36e97-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="36e97-106">Explorer (und der Bericht über Echt Zeit Erkennungen) zeigt Informationen zu mutmaßlicher Schadsoftware und Phishing in e-Mails und Dateien in Office 365 sowie andere Sicherheitsrisiken und Risiken für Ihre Organisation an.</span><span class="sxs-lookup"><span data-stu-id="36e97-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="36e97-107">Wenn Sie [Microsoft Defender für Office 365](office-365-atp.md) Plan 2 haben, haben Sie den Explorer.</span><span class="sxs-lookup"><span data-stu-id="36e97-107">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="36e97-108">Wenn Sie Microsoft Defender für Office 365 Plan 1 haben, haben Sie Echt Zeit Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="36e97-108">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="36e97-109">Wenn Sie Explorer zum ersten Mal öffnen (oder den Bericht über Echt Zeit Erkennungen), werden in der Standardansicht e-Mail-Malwareerkennungen für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36e97-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="36e97-110">In diesem Bericht kann auch Microsoft Defender für Office 365 Erkennungen angezeigt werden, beispielsweise bösartige URLs, die von [sicheren Links](atp-safe-links.md)erkannt werden, und böswillige Dateien, die von [sicheren Anlagen](atp-safe-attachments.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="36e97-110">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="36e97-111">Dieser Bericht kann geändert werden, um Daten für die letzten 30 Tage anzuzeigen (mit einem Microsoft Defender für Office 365 kostenpflichtigen P2-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="36e97-111">This report can be modified to show data for the past 30 days (with an Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="36e97-112">Testabonnements enthalten nur Daten für die letzten sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="36e97-112">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="36e97-113">Abonnement</span><span class="sxs-lookup"><span data-stu-id="36e97-113">Subscription</span></span>|<span data-ttu-id="36e97-114">Dienstprogramm</span><span class="sxs-lookup"><span data-stu-id="36e97-114">Utility</span></span>|<span data-ttu-id="36e97-115">Tage mit Daten</span><span class="sxs-lookup"><span data-stu-id="36e97-115">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="36e97-116">Microsoft Defender für Office 365 P1-Testversion</span><span class="sxs-lookup"><span data-stu-id="36e97-116">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="36e97-117">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="36e97-117">Real-time detections</span></span>|<span data-ttu-id="36e97-118">7 </span><span class="sxs-lookup"><span data-stu-id="36e97-118">7</span></span>|
|<span data-ttu-id="36e97-119">Microsoft Defender für Office 365 P1 bezahlt</span><span class="sxs-lookup"><span data-stu-id="36e97-119">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="36e97-120">Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="36e97-120">Real-time detections</span></span>|<span data-ttu-id="36e97-121">30</span><span class="sxs-lookup"><span data-stu-id="36e97-121">30</span></span>|
|<span data-ttu-id="36e97-122">Microsoft Defender für Office 365 P1 Paid Test Defender für Office 365 P2-Testversion</span><span class="sxs-lookup"><span data-stu-id="36e97-122">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="36e97-123">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="36e97-123">Threat Explorer</span></span>|<span data-ttu-id="36e97-124">7 </span><span class="sxs-lookup"><span data-stu-id="36e97-124">7</span></span>|
|<span data-ttu-id="36e97-125">Microsoft Defender für Office 365 P2-Testversion</span><span class="sxs-lookup"><span data-stu-id="36e97-125">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="36e97-126">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="36e97-126">Threat Explorer</span></span>|<span data-ttu-id="36e97-127">7 </span><span class="sxs-lookup"><span data-stu-id="36e97-127">7</span></span>|
|<span data-ttu-id="36e97-128">Microsoft Defender für Office 365 P2 bezahlt</span><span class="sxs-lookup"><span data-stu-id="36e97-128">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="36e97-129">Sicherheitsrisiken-Explorer</span><span class="sxs-lookup"><span data-stu-id="36e97-129">Threat Explorer</span></span>|<span data-ttu-id="36e97-130">30</span><span class="sxs-lookup"><span data-stu-id="36e97-130">30</span></span>|
|

<span data-ttu-id="36e97-131">Verwenden Sie das Menü **Ansicht** , um zu ändern, welche Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36e97-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="36e97-132">Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="36e97-132">Tooltips help you determine which view to use.</span></span>

![Ansicht im Menü "Bedrohungs-Explorer"](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="36e97-134">Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um eine weitere Analyse durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="36e97-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="36e97-135">Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die in Explorer verfügbar sind (oder Echt Zeit Erkennungen).</span><span class="sxs-lookup"><span data-stu-id="36e97-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="36e97-136">E-Mail-> Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="36e97-136">Email > Malware</span></span>

<span data-ttu-id="36e97-137">Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View** die Option  >  **e-Mail-**  >  **Schadsoftware** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-137">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="36e97-138">In dieser Ansicht werden Informationen zu e-Mail-Nachrichten angezeigt, die als mit Schadsoftware gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="36e97-138">This view shows information about email messages that were identified as containing malware.</span></span>

![Anzeigen von Daten zu e-Mails, die als Schadsoftware identifiziert wurden](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="36e97-140">Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36e97-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="36e97-141">Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und vielem mehr anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36e97-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="36e97-142">Um beispielsweise zu sehen, welche Aktionen bei erkannten e-Mail-Nachrichten durchgeführt wurden, wählen Sie in der Liste **Schutzstatus** aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="36e97-143">Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche Aktualisieren, um diesen Filter auf Ihren Bericht anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="36e97-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Bedrohungsschutz-Status Optionen für Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="36e97-145">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="36e97-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="36e97-146">Wenn Sie ein Element in der Liste auswählen, wird ein Ausklappbereich geöffnet, in dem Sie weitere Informationen zum ausgewählten Element erhalten.</span><span class="sxs-lookup"><span data-stu-id="36e97-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Threat Explorer mit geöffnetem Flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="36e97-148">E-Mail > Phishing</span><span class="sxs-lookup"><span data-stu-id="36e97-148">Email > Phish</span></span>

<span data-ttu-id="36e97-149">Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View** die Option  >  **e-Mail-**  >  **Phishing** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-149">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="36e97-150">Diese Ansicht zeigt e-Mail-Nachrichten, die als Phishing-Versuche identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="36e97-150">This view shows email messages identified as phishing attempts.</span></span>

![Anzeigen von Daten zu e-Mails, die als Phishing-Versuche identifiziert wurden](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="36e97-152">Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36e97-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="36e97-153">Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Absender-IP, URL-Domäne, Klick Urteil und vieles mehr anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36e97-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="36e97-154">Um beispielsweise zu sehen, welche Aktionen durchgeführt wurden, als Personen auf URLs geklickt haben, die als Phishing-Versuche identifiziert wurden, wählen Sie in der Liste **auf Urteil klicken** , wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="36e97-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicken Sie auf Urteils Optionen für den Phish-Bericht](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="36e97-156">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und e-Mail-Ursprung an.</span><span class="sxs-lookup"><span data-stu-id="36e97-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![Als Phishing erkannte URLs in e-Mail-Nachrichten](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="36e97-158">Wenn Sie ein Element in der Liste auswählen, beispielsweise eine erkannte URL, wird ein Ausklappbereich geöffnet, in dem Sie weitere Informationen zum ausgewählten Element erhalten.</span><span class="sxs-lookup"><span data-stu-id="36e97-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="36e97-160">E-Mail > Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="36e97-160">Email > Submissions</span></span>

<span data-ttu-id="36e97-161">Um diesen Bericht anzuzeigen, wählen Sie im Explorer (oder Echtzeiterkennung) die Option **View**  >  **e-Mail-**  >  **Übermittlungen** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-161">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="36e97-162">In dieser Ansicht werden e-Mails angezeigt, die Benutzer als Junk-e-Mail, nicht als Junk oder als Phishing-e-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="36e97-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Von Benutzern gemeldete e-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="36e97-164">Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36e97-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="36e97-165">Verwenden Sie diese Liste, um Informationen nach Absender, Empfänger, Berichtstyp anzuzeigen (die Bestimmung des Benutzers, dass es sich bei der e-Mail um Junk-e-Mails handelte, nicht um Junk-oder Phishing-Zwecke) und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="36e97-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="36e97-166">Wenn Sie beispielsweise Informationen zu e-Mail-Nachrichten anzeigen möchten, die als Phishing-Versuche gemeldet wurden, klicken Sie auf **Absender**  >  **Berichtstyp** , wählen Sie **Phishing** aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="36e97-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type** , select **Phish** , and then click the Refresh button.</span></span>

![Für den Berichtstyp Filter ausgewählter Phishing-Typ](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="36e97-168">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten e-Mail-Nachrichten an, beispielsweise Betreffzeile, die IP-Adresse des Absenders, den Benutzer, der die Nachricht als Junk-e-Mail, nicht Junk oder Phishing gemeldet hat, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="36e97-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Nachrichten, die als Phishing-Versuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="36e97-170">Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36e97-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="36e97-171">E-Mail > alle e-Mails</span><span class="sxs-lookup"><span data-stu-id="36e97-171">Email > All email</span></span>

<span data-ttu-id="36e97-172">Um diesen Bericht anzuzeigen, wählen Sie im Explorer **View** die Option  >  **e-Mail**  >  **alle e-Mails** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-172">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="36e97-173">Diese Ansichten zeigen eine Gesamtansicht der e-Mail-Aktivität an, einschließlich e-Mails, die aufgrund von Phishing oder Schadsoftware als bösartig eingestuft wurden, sowie alle nicht-böswilligen e-Mails (normale e-Mail, Spam und Massen-e-Mails).</span><span class="sxs-lookup"><span data-stu-id="36e97-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="36e97-174">Wenn Sie eine Fehlermeldung erhalten, die zu **viele anzuzeigende Daten** liest, fügen Sie einen Filter hinzu, und verringern Sie ggf. den von Ihnen angezeigten Datumsbereich.</span><span class="sxs-lookup"><span data-stu-id="36e97-174">If you get an error that reads **Too much data to display** , add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="36e97-175">Wenn Sie einen Filter anwenden möchten, wählen Sie **Absender** aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="36e97-175">To apply a filter, choose **Sender** , select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="36e97-176">In unserem Beispiel haben wir die **Erkennungstechnologie** als Filter verwendet (es stehen verschiedene Optionen zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="36e97-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="36e97-177">Anzeigen von Informationen nach Absender, Domäne des Absenders, Empfänger, Betreff, Anlagendateiname, Malwarefamilie, Schutzstatus (Aktionen, die von den Bedrohungen geschützt sind, und Richtlinien in Office 365), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="36e97-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Anzeigen von Daten zu erkannten e-Mails anhand von Erkennungstechnologien](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="36e97-179">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten e-Mail-Nachrichten an, beispielsweise Betreff, Empfänger, Absender, Status usw.</span><span class="sxs-lookup"><span data-stu-id="36e97-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="36e97-180">Inhalte > Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="36e97-180">Content > Malware</span></span>

<span data-ttu-id="36e97-181">Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View** die Option  >  **Inhalts**  >  **Malware** anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="36e97-181">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="36e97-182">In dieser Ansicht werden Dateien angezeigt, die von [Microsoft Defender für Office 365 in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams](atp-for-spo-odb-and-teams.md)als böswillig identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="36e97-182">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="36e97-183">Anzeigen von Informationen nach Malwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Arbeitsauslastung (OneDrive, SharePoint oder Teams).</span><span class="sxs-lookup"><span data-stu-id="36e97-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Anzeigen von Daten zu erkannter Schadsoftware](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="36e97-185">Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Dateien an, beispielsweise Anlagendateiname, Arbeitsauslastung, Dateigröße, wer die Datei zuletzt geändert hat und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="36e97-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="36e97-186">Click-to-Filter-Funktionen</span><span class="sxs-lookup"><span data-stu-id="36e97-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="36e97-187">Mit Explorer (und Echtzeiterkennung) können Sie einen Filter in einem Klick anwenden.</span><span class="sxs-lookup"><span data-stu-id="36e97-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="36e97-188">Klicken Sie auf ein Element in der Legende, und dieses Element wird zum Filter für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="36e97-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="36e97-189">Nehmen wir beispielsweise an, dass wir uns die Malware-Ansicht im Explorer ansehen:</span><span class="sxs-lookup"><span data-stu-id="36e97-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Wechseln Sie zu Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="36e97-191">Wenn Sie in diesem Diagramm auf **ATP-Detonation** klicken, wird eine Ansicht wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="36e97-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer gefiltert, um nur Defender für Office 365 detonations Ergebnisse anzuzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="36e97-193">In dieser Ansicht betrachten wir nun Daten für Dateien, die mit [sicheren Anlagen](atp-safe-attachments.md)gezündet wurden.</span><span class="sxs-lookup"><span data-stu-id="36e97-193">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="36e97-194">Unter dem Diagramm können Details zu bestimmten e-Mail-Nachrichten mit Anlagen angezeigt werden, die von sicheren Anlagen erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="36e97-194">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Spezifische Details zu e-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="36e97-196">Wenn Sie ein oder mehrere Elemente auswählen, wird das Menü **Aktionen** aktiviert, das mehrere Auswahlmöglichkeiten für die ausgewählten Elemente bietet.</span><span class="sxs-lookup"><span data-stu-id="36e97-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Durch die Auswahl eines Elements wird das Menü Aktionen aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="36e97-198">Die Möglichkeit, mit einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen viel Zeit bei der Untersuchung von Bedrohungen sparen.</span><span class="sxs-lookup"><span data-stu-id="36e97-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="36e97-199">Abfragen und Filter</span><span class="sxs-lookup"><span data-stu-id="36e97-199">Queries and filters</span></span>

<span data-ttu-id="36e97-200">Explorer (sowie der Bericht über Echt Zeit Erkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie Details eingehen können, beispielsweise Top-Zielbenutzer, Top-Malware Familien, Erkennungstechnologien und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="36e97-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="36e97-201">Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Durchsuchen von Daten.</span><span class="sxs-lookup"><span data-stu-id="36e97-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36e97-202">Verwenden Sie in der Abfrage Leiste für Explorer (oder Echtzeiterkennung) keine Platzhalterzeichen, beispielsweise ein Sternchen oder ein Fragezeichen.</span><span class="sxs-lookup"><span data-stu-id="36e97-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="36e97-203">Wenn Sie im **Feld Betreff** nach e-Mail-Nachrichten suchen, führt der Explorer (oder Echt Zeit Erkennungsvorgang) partielle Übereinstimmungen und Ergebnis Ergebnisse aus, die einer Platzhaltersuche ähneln.</span><span class="sxs-lookup"><span data-stu-id="36e97-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
