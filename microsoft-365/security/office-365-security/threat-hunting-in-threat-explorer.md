---
title: Bedrohungssuche im Bedrohungs-Explorer für Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Verwenden Sie den Bedrohungs-Explorer oder Echtzeiterkennungen im Microsoft 365 Defender Portal, um Bedrohungen effizient zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b0c0c36cb481aac64b55467da4aaf9e3cf7a493
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083560"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="63368-103">Bedrohungssuche im Bedrohungs-Explorer für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="63368-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="63368-104">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="63368-104">In this article:</span></span>

- [<span data-ttu-id="63368-105">Exemplarische Vorgehensweise im Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="63368-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="63368-106">E-Mail-Untersuchung</span><span class="sxs-lookup"><span data-stu-id="63368-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="63368-107">E-Mail-Korrektur</span><span class="sxs-lookup"><span data-stu-id="63368-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="63368-108">Verbesserungen bei der Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="63368-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="63368-109">Dies ist Teil einer **Drei-Artikel-Reihe** zu Den Grundlagen von **Bedrohungs-Explorer (Explorer),** **E-Mail-Sicherheit** und **Explorer und Echtzeiterkennungen** (z. B. Unterschiede zwischen den Tools und berechtigungen, die zum Ausführen dieser Tools erforderlich sind).</span><span class="sxs-lookup"><span data-stu-id="63368-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="63368-110">Die anderen beiden Artikel dieser Reihe sind [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md) und [Dem Bedrohungs-Explorer und den Grundlagen der Echtzeiterkennung.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="63368-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="63368-111">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="63368-111">**Applies to**</span></span>
- [<span data-ttu-id="63368-112">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="63368-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="63368-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63368-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="63368-114">Wenn Ihre Organisation [über Microsoft Defender für Office 365](defender-for-office-365.md)verfügt und Sie über die [Berechtigungen](#required-licenses-and-permissions)verfügen, können Sie **Explorer-** oder **Echtzeiterkennungen** verwenden, um Bedrohungen zu erkennen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="63368-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="63368-115">Wechseln **Sie** im Microsoft 365 Defender Portal zu **E-Mail & Zusammenarbeit,** und wählen Sie dann **Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="63368-115">In the **Microsoft 365 Defender portal**, go to **Email & collaboration**, and then choose **Explorer**.</span></span>

<br>

****

|<span data-ttu-id="63368-116">Mit Microsoft Defender für Office 365 Plan 2 sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63368-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="63368-117">Mit Microsoft Defender für Office 365 Plan 1 sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63368-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Bedrohungs-Explorer](../../media/path-to-explorer.png)|![Echtzeiterkennungen](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="63368-120">Mit diesen Tools können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="63368-120">With these tools, you can:</span></span>

- <span data-ttu-id="63368-121">Anzeigen von Schadsoftware, die von Microsoft 365 Sicherheitsfeatures erkannt wurde</span><span class="sxs-lookup"><span data-stu-id="63368-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="63368-122">Phishing-URL anzeigen und auf Bewertungsdaten klicken</span><span class="sxs-lookup"><span data-stu-id="63368-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="63368-123">Starten eines automatisierten Untersuchungs- und Antwortprozesses aus einer Ansicht im Explorer</span><span class="sxs-lookup"><span data-stu-id="63368-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="63368-124">Untersuchen bösartiger E-Mails und vieles mehr</span><span class="sxs-lookup"><span data-stu-id="63368-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="63368-125">Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="63368-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="63368-126">Exemplarische Vorgehensweise im Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="63368-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="63368-127">In Microsoft Defender für Office 365 gibt es zwei Abonnementpläne: Plan 1 und Plan 2.</span><span class="sxs-lookup"><span data-stu-id="63368-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="63368-128">Manuell betriebene Bedrohungssuche-Tools sind in beiden Plänen vorhanden, unter unterschiedlichen Namen und mit unterschiedlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="63368-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="63368-129">Defender für Office 365 Plan 1 verwendet *Echtzeiterkennungen,* bei denen es sich um eine Teilmenge des *Bedrohungs-Explorer-Suchtools* (auch *Explorer* genannt) in Plan 2 handelt.</span><span class="sxs-lookup"><span data-stu-id="63368-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="63368-130">In dieser Artikelreihe wurden die meisten Beispiele mithilfe des vollständigen Bedrohungs-Explorers erstellt.</span><span class="sxs-lookup"><span data-stu-id="63368-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="63368-131">Administratoren sollten alle Schritte in Echtzeiterkennungen testen, um zu sehen, wo sie sich befinden.</span><span class="sxs-lookup"><span data-stu-id="63368-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="63368-132">Um das Explorer-Tool zu öffnen, wechseln Sie zu **Microsoft 365 Defender Portal**  >  **E-Mail & Zusammenarbeits-Explorer.**  >  </span><span class="sxs-lookup"><span data-stu-id="63368-132">To open the Explorer tool, go to **Microsoft 365 Defender portal** > **Email & collaboration** > **Explorer**.</span></span> <span data-ttu-id="63368-133">Standardmäßig gelangen Sie auf der Seite **"Schadsoftware",** verwenden aber die Dropdownliste **"Ansicht",** um sich mit Ihren Optionen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="63368-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="63368-134">Wenn Sie Phishing suchen oder sich mit einer Bedrohungskampagne befassen, wählen Sie diese Ansichten aus.</span><span class="sxs-lookup"><span data-stu-id="63368-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-135">![Ansichts-Dropdownliste im Bedrohungs-Explorer](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="63368-135">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="63368-136">Sobald eine Person für Sicherheitsvorgänge (Sec Ops) die Daten auswählt, die sie anzeigen möchten, ob der Bereich eine schmale Ansicht wie **Benutzerübermittlungen** oder eine breitere Ansicht wie **"Alle E-Mails"** ist, kann er die Schaltfläche **"Absender"** verwenden, um weiter zu filtern.</span><span class="sxs-lookup"><span data-stu-id="63368-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="63368-137">Denken Sie daran, "Aktualisieren" auszuwählen, um ihre Filteraktionen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="63368-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-138">![Absenderschaltfläche im Bedrohungs-Explorer](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="63368-138">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="63368-139">Die Verfeinerung des Fokus im Explorer oder der Echtzeiterkennung kann in Ebenen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="63368-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="63368-140">Die erste ist **View**.</span><span class="sxs-lookup"><span data-stu-id="63368-140">The first is **View**.</span></span> <span data-ttu-id="63368-141">Der zweite kann als *gefilterter Fokus* betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="63368-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="63368-142">Sie können beispielsweise die Schritte, die Sie bei der Suche nach einer Bedrohung ausgeführt haben, zurückziehen, indem Sie Ihre Entscheidungen wie folgt aufzeichnen: Um das Problem im Explorer zu finden, **habe ich die Schadsoftwareansicht mit einem Empfängerfilterfokus ausgewählt.**</span><span class="sxs-lookup"><span data-stu-id="63368-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="63368-143">Dies erleichtert das Zurückziehen Ihrer Schritte.</span><span class="sxs-lookup"><span data-stu-id="63368-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="63368-144">Wenn Sec Ops **Tags** verwendet, um Konten zu markieren, die sie als hochwertige Ziele betrachten, können sie Auswahlen wie *die Phishingansicht mit einem Tags-Filterfokus treffen (bei Verwendung einen Datumsbereich einschließen).*</span><span class="sxs-lookup"><span data-stu-id="63368-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="63368-145">Dadurch werden alle Phishing-Versuche angezeigt, die während eines Bestimmten Zeitraums an ihre hochwertigen Benutzerziele gerichtet sind (z. B. Datumsangaben, an denen bestimmte Phishingangriffe für ihre Branche häufig ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="63368-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="63368-146">Mithilfe der Datumsbereichssteuerelemente können Einschränkungen für Datumsbereiche vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="63368-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="63368-147">Hier sehen Sie den Explorer in der **Schadsoftwareansicht** mit einem Filterfokus **der Erkennungstechnologie.**</span><span class="sxs-lookup"><span data-stu-id="63368-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="63368-148">Aber es ist die **Erweiterte Filterschaltfläche,** mit der Sec Ops-Teams tief graben können.</span><span class="sxs-lookup"><span data-stu-id="63368-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-149">![Erweiterter Filter im Bedrohungs-Explorer](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="63368-149">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="63368-150">Durch Klicken auf den **Erweiterten Filter** wird ein Bereich angezeigt, in dem Sec Ops-Schützer selbst Abfragen erstellen können, sodass sie die benötigten Informationen einschließen oder ausschließen können.</span><span class="sxs-lookup"><span data-stu-id="63368-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="63368-151">Sowohl das Diagramm als auch die Tabelle auf der Explorer-Seite spiegeln ihre Ergebnisse wider.</span><span class="sxs-lookup"><span data-stu-id="63368-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-152">![Ergebnisse einer Abfrage](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="63368-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="63368-153">Verwenden Sie die Schaltfläche **"Spaltenoptionen",** um die Art von Informationen in der Tabelle abzurufen, die am hilfreichsten wären:</span><span class="sxs-lookup"><span data-stu-id="63368-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-154">![Schaltfläche "Spaltenoptionen" hervorgehoben](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="63368-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-155">![Verfügbare Optionen in Spalten](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="63368-155">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="63368-156">Stellen Sie sicher, dass Sie ihre Anzeigeoptionen in derselben Miene testen.</span><span class="sxs-lookup"><span data-stu-id="63368-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="63368-157">Unterschiedliche Zielgruppen reagieren gut auf unterschiedliche Präsentationen derselben Daten.</span><span class="sxs-lookup"><span data-stu-id="63368-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="63368-158">Für einige Besucher kann die **Karte "E-Mail-Ursprünge"** zeigen, dass eine Bedrohung weit verbreitet oder schneller als die **Anzeigeoption "Kampagne"** direkt daneben verbreitet ist.</span><span class="sxs-lookup"><span data-stu-id="63368-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="63368-159">Sec Ops können diese Displays verwenden, um am besten Punkte zu machen, die die Notwendigkeit von Sicherheit und Schutz unterstreichen, oder für einen späteren Vergleich, um die Effektivität ihrer Aktionen zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="63368-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-160">![Karte "E-Mail-Ursprünge"](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="63368-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-161">![Optionen für die Kampagnenanzeige](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="63368-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="63368-162">E-Mail-Untersuchung</span><span class="sxs-lookup"><span data-stu-id="63368-162">Email investigation</span></span>

<span data-ttu-id="63368-163">Wenn eine verdächtige E-Mail angezeigt wird, klicken Sie auf den Namen, um das Flyout auf der rechten Seite zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="63368-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="63368-164">Hier ist das Banner verfügbar, mit dem Sec Ops die [E-Mail-Entitätsseite](mdo-email-entity-page.md) anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="63368-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="63368-165">Die Seite "E-Mail-Entität" zieht Inhalte zusammen, die unter **Details,** **Anlagen,** **Geräte,** aber besser organisierten Daten zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="63368-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="63368-166">Dazu gehören Dinge wie DMARC-Ergebnisse, nur-Text-Anzeige des E-Mail-Headers mit einer Kopieroption, Bewertungsinformationen zu Anlagen, die sicher detoniert wurden, und Dateien, die verworfen wurden (einschließlich IP-Adressen, die kontaktiert wurden, und Screenshots von Seiten oder Dateien).</span><span class="sxs-lookup"><span data-stu-id="63368-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="63368-167">URLs und ihre Bewertungen werden ebenfalls mit ähnlichen Details aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="63368-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="63368-168">Wenn Sie diese Phase erreichen, ist die Seite "E-Mail-Entität" für den letzten Schritt wichtig:*Die Behebung.*</span><span class="sxs-lookup"><span data-stu-id="63368-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-169">![Die E-Mail-Entitätsseite](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="63368-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="63368-170&quot;>Um mehr über die Rich-E-Mail-Entitätsseite (siehe unten auf der Registerkarte **&quot;Analyse")** zu erfahren, einschließlich der Ergebnisse der detonierten Anlagen, der Ergebnisse für die enthaltenen URLs und der sicheren E-Mail-Vorschau, klicken Sie [hier.](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="63368-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-171">![Registerkarte "Analyse" der E-Mail-Entitätsseite](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="63368-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="63368-172">E-Mail-Korrektur</span><span class="sxs-lookup"><span data-stu-id="63368-172">Email remediation</span></span>

<span data-ttu-id="63368-173">Sobald eine Sec Ops-Person feststellt, dass eine E-Mail eine Bedrohung ist, befasst sich der nächste Explorer- oder Echtzeiterkennungsschritt mit der Bedrohung und deren Behebung.</span><span class="sxs-lookup"><span data-stu-id="63368-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="63368-174">Dies kann erfolgen, indem Sie zum Bedrohungs-Explorer zurückkehren, das Kontrollkästchen für die problematische E-Mail aktivieren und die Schaltfläche **"Aktionen"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="63368-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-175">![Schaltfläche "Aktionen" im Bedrohungs-Explorer](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="63368-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="63368-176">Hier kann der Analyst Aktionen wie das Melden der E-Mail als Spam, Phishing oder Schadsoftware, das Kontaktieren von Empfängern oder weitere Untersuchungen ausführen, die das Auslösen von Playbooks für automatische Untersuchung und Reaktion (Automated Investigation and Response, AIR) umfassen können (wenn Sie über Plan 2 verfügen).</span><span class="sxs-lookup"><span data-stu-id="63368-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="63368-177">Oder die E-Mail kann auch als sauber gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="63368-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-178">![Die Dropdownliste "Aktionen"](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="63368-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="63368-179">Verbesserungen bei der Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="63368-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="63368-180">Warnungs-ID</span><span class="sxs-lookup"><span data-stu-id="63368-180">Alert ID</span></span>

<span data-ttu-id="63368-181">Wenn Sie von einer Warnung zum Bedrohungs-Explorer navigieren, wird die **Ansicht** nach **Warnungs-ID** gefiltert.</span><span class="sxs-lookup"><span data-stu-id="63368-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="63368-182">Dies gilt auch für die Echtzeiterkennung.</span><span class="sxs-lookup"><span data-stu-id="63368-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="63368-183">Nachrichten, die für die jeweilige Warnung relevant sind, und eine E-Mail-Gesamtsumme (eine Anzahl) werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="63368-184">Sie können sehen, ob eine Nachricht Teil einer Warnung war, und von dieser Nachricht zu der zugehörigen Warnung navigieren.</span><span class="sxs-lookup"><span data-stu-id="63368-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="63368-185">Schließlich ist die Warnungs-ID in der URL enthalten, z. B.: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="63368-185">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-186">![Filtern nach Warnungs-ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="63368-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-187">![Warnungs-ID im Detail-Flyout](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="63368-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="63368-188">Erweitern des Explorer-Datenaufbewahrungs- und Suchlimits für Testmandanten (und Echtzeiterkennungen)</span><span class="sxs-lookup"><span data-stu-id="63368-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="63368-189">Im Rahmen dieser Änderung können Analysten E-Mail-Daten innerhalb von 30 Tagen (von sieben Tagen) im Bedrohungs-Explorer und in Echtzeiterkennungen für Defender für Office P1- und P2-Testmandanten suchen und filtern.</span><span class="sxs-lookup"><span data-stu-id="63368-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="63368-190">Dies wirkt sich nicht auf Produktionsmandanten für P1- und P2 E5-Kunden aus, bei denen der Aufbewahrungsstandard bereits 30 Tage beträgt.</span><span class="sxs-lookup"><span data-stu-id="63368-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="63368-191">Exportgrenzwert aktualisiert</span><span class="sxs-lookup"><span data-stu-id="63368-191">Updated Export limit</span></span> 

<span data-ttu-id="63368-192">Die Anzahl der E-Mail-Einträge, die aus dem Bedrohungs-Explorer exportiert werden können, beträgt jetzt 200.000 (war 9990).</span><span class="sxs-lookup"><span data-stu-id="63368-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="63368-193">Der Satz von Spalten, die exportiert werden können, ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="63368-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="63368-194">Tags im Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="63368-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="63368-195">Das Feature "Benutzertags" befindet sich in der Vorschau und ist möglicherweise nicht für alle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63368-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="63368-196">Außerdem können Vorschauen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63368-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="63368-197">Informationen zum Veröffentlichungszeitplan finden Sie in der roadmap für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63368-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="63368-198">Benutzertags identifizieren bestimmte Benutzergruppen in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="63368-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="63368-199">Weitere Informationen zu Tags, einschließlich Lizenzierung und Konfiguration, finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="63368-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="63368-200">Im Bedrohungs-Explorer können Sie Informationen zu Benutzertags in den folgenden Oberflächen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="63368-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="63368-201">E-Mail-Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="63368-201">Email grid view</span></span>

<span data-ttu-id="63368-202">Wenn Analysten die **Tagsspalte** im E-Mail-Raster betrachten, sehen sie alle Tags, die auf Absender- oder Empfängerpostfächer angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="63368-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="63368-203">Standardmäßig werden zuerst Systemtags wie *Prioritätskonten* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-204">![Filtern von Tags in der E-Mail-Rasteransicht](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="63368-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="63368-205">Filtern</span><span class="sxs-lookup"><span data-stu-id="63368-205">Filtering</span></span>

<span data-ttu-id="63368-206">Tags können als Filter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63368-206">Tags can be used as filters.</span></span> <span data-ttu-id="63368-207">Suchen Sie nur zwischen Prioritätskonten, oder verwenden Sie bestimmte Benutzertagszenarien auf diese Weise.</span><span class="sxs-lookup"><span data-stu-id="63368-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="63368-208">Sie können auch Ergebnisse mit bestimmten Tags ausschließen.</span><span class="sxs-lookup"><span data-stu-id="63368-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="63368-209">Kombinieren Sie Tags mit anderen Filtern und Datumsbereichen, um den Untersuchungsbereich einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="63368-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="63368-210">[![Filtertags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="63368-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-211">![Keine Filtertags](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="63368-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="63368-212">Flyout für E-Mail-Details</span><span class="sxs-lookup"><span data-stu-id="63368-212">Email detail flyout</span></span>

<span data-ttu-id="63368-213">Um die einzelnen Tags für Absender und Empfänger anzuzeigen, wählen Sie eine E-Mail aus, um das Flyout mit den Nachrichtendetails zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="63368-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="63368-214">Auf der Registerkarte **"Zusammenfassung"** werden die Absender- und Empfängertags separat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="63368-215">Die Informationen zu einzelnen Tags für Absender und Empfänger können als CSV-Daten exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="63368-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-216">![E-Mail-Details-Tags](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="63368-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="63368-217">Tags-Informationen werden auch im Flyout für URL-Klicks angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="63368-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Wählen Sie ein einzelnes URL-Flyout aus, um weitere Details zu Klicks für diese URL anzuzeigen, einschließlich aller Tags, die diesem Klick zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="63368-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="63368-219">Aktualisierte Zeitachsenansicht</span><span class="sxs-lookup"><span data-stu-id="63368-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-220">![URL-Tags](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="63368-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="63368-221">Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4) ansehen.</span><span class="sxs-lookup"><span data-stu-id="63368-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="63368-222">Erweiterte Funktionen</span><span class="sxs-lookup"><span data-stu-id="63368-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="63368-223">Benutzer mit den wichtigsten Zielen</span><span class="sxs-lookup"><span data-stu-id="63368-223">Top targeted users</span></span>

<span data-ttu-id="63368-224">Die wichtigsten Schadsoftwarefamilien zeigen die **am häufigsten verwendeten Benutzer** im Abschnitt "Schadsoftware" an.</span><span class="sxs-lookup"><span data-stu-id="63368-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="63368-225">Die wichtigsten Benutzer werden auch über Phishing- und alle E-Mail-Ansichten erweitert.</span><span class="sxs-lookup"><span data-stu-id="63368-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="63368-226">Analysten können die fünf wichtigsten Zielbenutzer zusammen mit der Anzahl der Versuche für jeden Benutzer in jeder Ansicht sehen.</span><span class="sxs-lookup"><span data-stu-id="63368-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="63368-227">Personen mit Sicherheitsvorgängen können die Liste der Zielbenutzer bis zu einem Grenzwert von 3.000 sowie die Anzahl der versuche für die Offlineanalyse für jede E-Mail-Ansicht exportieren.</span><span class="sxs-lookup"><span data-stu-id="63368-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="63368-228">Wenn Sie außerdem die Anzahl der Versuche auswählen (z. B. 13 Versuche in der abbildung unten), wird im Bedrohungs-Explorer eine gefilterte Ansicht geöffnet, sodass Sie weitere Details zu E-Mails und Bedrohungen für diesen Benutzer sehen können.</span><span class="sxs-lookup"><span data-stu-id="63368-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-229">![Benutzer mit den wichtigsten Zielen](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="63368-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="63368-230">Exchange-Transportregeln</span><span class="sxs-lookup"><span data-stu-id="63368-230">Exchange transport rules</span></span>

<span data-ttu-id="63368-231">Das Sicherheitsteam kann alle auf eine Nachricht angewendeten Exchange Transportregeln (oder Nachrichtenflussregeln) in der E-Mail-Rasteransicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="63368-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="63368-232">Wählen Sie im Raster **Spaltenoptionen** aus, und fügen Sie dann in den Spaltenoptionen **Exchange Transportregel** hinzu.</span><span class="sxs-lookup"><span data-stu-id="63368-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="63368-233">Die Option Exchange Transportregeln ist auch im **Flyout "Details"** in der E-Mail sichtbar.</span><span class="sxs-lookup"><span data-stu-id="63368-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="63368-234">Namen und GUIDs der Transportregeln, die auf die Nachricht angewendet wurden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="63368-235">Analysten können mithilfe des Namens der Transportregel nach Nachrichten suchen.</span><span class="sxs-lookup"><span data-stu-id="63368-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="63368-236">Hierbei handelt es sich um eine CONTAINS-Suche, was bedeutet, dass Sie auch teilsuchen können.</span><span class="sxs-lookup"><span data-stu-id="63368-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="63368-237">Exchange Verfügbarkeit von Transportregelsuch- und -namen hängt von der ihnen zugewiesenen Rolle ab.</span><span class="sxs-lookup"><span data-stu-id="63368-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="63368-238">Sie benötigen eine der folgenden Rollen oder Berechtigungen, um die Transportregelnamen und die Suche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="63368-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="63368-239">Auch ohne die unten aufgeführten Rollen oder Berechtigungen werden einem Analysten möglicherweise die Transportregelbezeichnung und guid-Informationen in den E-Mail-Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="63368-240">Andere Funktionen zum Anzeigen von Datensätzen in E-Mail-Rastern, E-Mail-Flyouts, Filtern und Exporten sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="63368-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="63368-241">Exchange Online Nur – Verhinderung von Datenverlust: Alle</span><span class="sxs-lookup"><span data-stu-id="63368-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="63368-242">Exchange Online Nur – O365SupportViewConfig: Alle</span><span class="sxs-lookup"><span data-stu-id="63368-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="63368-243">Microsoft Azure Active Directory oder Exchange Online – Sicherheitsadministrator: Alle</span><span class="sxs-lookup"><span data-stu-id="63368-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="63368-244">Azure Active Directory oder Exchange Online – Sicherheitsleseberechtigter: Alle</span><span class="sxs-lookup"><span data-stu-id="63368-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="63368-245">Exchange Online Nur – Transportregeln: Alle</span><span class="sxs-lookup"><span data-stu-id="63368-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="63368-246">Exchange Online Only - View-Only Configuration: All</span><span class="sxs-lookup"><span data-stu-id="63368-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="63368-247">Innerhalb des E-Mail-Rasters, des Detail-Flyouts und der exportierten CSV-Datei wird den ETRs wie unten dargestellt ein Name/eine GUID angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63368-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="63368-248">![Exchange Transportregeln](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="63368-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="63368-249">Eingehende Connectors</span><span class="sxs-lookup"><span data-stu-id="63368-249">Inbound connectors</span></span>

<span data-ttu-id="63368-250">Connectors sind eine Sammlung von Anweisungen, die anpassen, wie Ihre E-Mails zu und von Ihrer Microsoft 365 oder Office 365 Organisation fließen.</span><span class="sxs-lookup"><span data-stu-id="63368-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="63368-251">Sie ermöglichen es Ihnen, alle Sicherheitseinschränkungen oder Steuerelemente anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="63368-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="63368-252">Im Bedrohungs-Explorer können Sie die Connectors anzeigen, die sich auf eine E-Mail beziehen, und mithilfe von Connectornamen nach E-Mails suchen.</span><span class="sxs-lookup"><span data-stu-id="63368-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="63368-253">Die Suche nach Connectors ist eine CONTAINS-Abfrage, was bedeutet, dass teilweise Schlüsselwortsuchen funktionieren können:</span><span class="sxs-lookup"><span data-stu-id="63368-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63368-254">![Connectordetails](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="63368-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="63368-255">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="63368-255">Required licenses and permissions</span></span>

<span data-ttu-id="63368-256">Sie benötigen [Microsoft Defender,](defender-for-office-365.md) damit Office 365 Explorer- oder Echtzeiterkennungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="63368-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="63368-257">Explorer ist in Defender für Office 365 Plan 2 enthalten.</span><span class="sxs-lookup"><span data-stu-id="63368-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="63368-258">Der Bericht über Echtzeiterkennungen ist in Defender für Office 365 Plan 1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="63368-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="63368-259">Planen Sie, Lizenzen für alle Benutzer zuzuweisen, die von Defender für Office 365 geschützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="63368-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="63368-260">Explorer- und Echtzeiterkennungen zeigen Erkennungsdaten für lizenzierte Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="63368-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="63368-261">Um Explorer- oder Echtzeiterkennungen anzuzeigen und zu verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63368-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="63368-262">Für das Microsoft 365 Defender-Portal:</span><span class="sxs-lookup"><span data-stu-id="63368-262">For the Microsoft 365 Defender portal:</span></span>

  - <span data-ttu-id="63368-263">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="63368-263">Organization Management</span></span>
  - <span data-ttu-id="63368-264">Sicherheitsadministrator (kann im Azure Active Directory Admin Center ( ) zugewiesen werden. <https://aad.portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="63368-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="63368-265">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="63368-265">Security Reader</span></span>

- <span data-ttu-id="63368-266">Für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="63368-266">For Exchange Online:</span></span>

  - <span data-ttu-id="63368-267">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="63368-267">Organization Management</span></span>
  - <span data-ttu-id="63368-268">Organisationsverwaltung – nur Leserechte</span><span class="sxs-lookup"><span data-stu-id="63368-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="63368-269">Schreibgeschützte Empfänger</span><span class="sxs-lookup"><span data-stu-id="63368-269">View-Only Recipients</span></span>
  - <span data-ttu-id="63368-270">Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="63368-270">Compliance Management</span></span>

<span data-ttu-id="63368-271">Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="63368-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="63368-272">Berechtigungen im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="63368-272">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="63368-273">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="63368-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="63368-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="63368-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="63368-275">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63368-275">More information</span></span>

- [<span data-ttu-id="63368-276">Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden</span><span class="sxs-lookup"><span data-stu-id="63368-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="63368-277">Anzeigen schädlicher Dateien, die in SharePoint Online, OneDrive und Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="63368-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="63368-278">Abrufen einer Übersicht über die Ansichten im Bedrohungs-Explorer (und Echtzeiterkennungen)</span><span class="sxs-lookup"><span data-stu-id="63368-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="63368-279">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="63368-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="63368-280">Automatische Untersuchung und Reaktion in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="63368-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="63368-281">Untersuchen von E-Mails mit der Seite "E-Mail-Entität"</span><span class="sxs-lookup"><span data-stu-id="63368-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)