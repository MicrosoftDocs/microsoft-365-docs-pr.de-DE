---
title: Bedrohungssuche im Threat Explorer für Microsoft Defender für Office 365
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
description: Verwenden Sie Threat Explorer oder Echtzeiterkennungen im Security Compliance Center, um Bedrohungen effizient &amp; zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295268"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="d3c4c-103">Bedrohungssuche im Threat Explorer für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d3c4c-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="d3c4c-104">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-104">In this article:</span></span>

- [<span data-ttu-id="d3c4c-105">Begeh-nen des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="d3c4c-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="d3c4c-106">E-Mail-Untersuchung</span><span class="sxs-lookup"><span data-stu-id="d3c4c-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="d3c4c-107">E-Mail-Korrektur</span><span class="sxs-lookup"><span data-stu-id="d3c4c-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="d3c4c-108">Verbesserungen bei der Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="d3c4c-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="d3c4c-109">Dies ist Teil einer **3-Artikel-Reihe** über Threat **Explorer (Explorer),** **E-Mail-Sicherheit** **und** Explorer- und Echtzeiterkennungsgrund grundlagen (z. B. Unterschiede zwischen den Tools und Berechtigungen, die für deren Betrieb erforderlich sind).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="d3c4c-110">Die anderen beiden Artikel in dieser Reihe sind [E-Mail-Sicherheit](real-time-detections.md) [mit Threat Explorer](email-security-in-microsoft-defender.md) und Threat Explorer und Grundlagen der Echtzeiterkennung.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="d3c4c-111">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="d3c4c-111">**Applies to**</span></span>
- [<span data-ttu-id="d3c4c-112">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="d3c4c-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d3c4c-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3c4c-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d3c4c-114">Wenn Ihre Organisation [über Microsoft Defender für Office 365](defender-for-office-365.md)verfügt und Sie über  die Berechtigungen [verfügen,](#required-licenses-and-permissions)können Sie **Explorer-** oder Echtzeiterkennungen verwenden, um Bedrohungen zu erkennen und zu abwehren.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="d3c4c-115">Wechseln Sie im **Security & Compliance Center** zu Bedrohungsverwaltung, und wählen Sie dann **Explorer-**  oder **Echtzeiterkennungen aus.** </span><span class="sxs-lookup"><span data-stu-id="d3c4c-115">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="d3c4c-116">Mit Microsoft Defender für Office 365 Plan 2 sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="d3c4c-117">Mit Microsoft Defender für Office 365 Plan 1 sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Bedrohungs-Explorer](../../media/threatmgmt-explorer.png)|![Echtzeiterkennungen](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="d3c4c-120">Mit diesen Tools können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-120">With these tools, you can:</span></span>

- <span data-ttu-id="d3c4c-121">Siehe Schadsoftware, die von Microsoft 365 erkannt wird</span><span class="sxs-lookup"><span data-stu-id="d3c4c-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="d3c4c-122">Anzeigen der Phishing-URL und Klicken auf Verdingungsdaten</span><span class="sxs-lookup"><span data-stu-id="d3c4c-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="d3c4c-123">Starten eines automatisierten Untersuchungs- und Reaktionsprozesses aus einer Ansicht im Explorer</span><span class="sxs-lookup"><span data-stu-id="d3c4c-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="d3c4c-124">Untersuchen bösartiger E-Mails und mehr</span><span class="sxs-lookup"><span data-stu-id="d3c4c-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="d3c4c-125">Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="d3c4c-126">Begeh-nen des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="d3c4c-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="d3c4c-127">In Microsoft Defender für Office 365 gibt es zwei Abonnementpläne: Plan 1 und Plan 2.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="d3c4c-128">Manuell betriebene Tools zur Bedrohungssuche sind in beiden Plänen unter unterschiedlichen Namen und mit unterschiedlichen Funktionen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="d3c4c-129">Defender for Office 365 Plan 1 verwendet Echtzeiterkennungen , die eine Teilmenge des *Bedrohungs-Explorers*(auch *Explorer* genannt) in Plan 2 ist. </span><span class="sxs-lookup"><span data-stu-id="d3c4c-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="d3c4c-130">In dieser Artikelreihe wurden die meisten Beispiele mit dem vollständigen Bedrohungs-Explorer erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="d3c4c-131">Administratoren sollten alle Schritte in Echtzeiterkennungen testen, um zu sehen, wo sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="d3c4c-132">Wechseln Sie zum Öffnen des Explorer-Tools zu **Security & Compliance Center** Threat  >  **Management**  >  **Explorer** (oder **Echtzeiterkennungen**).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-132">To open the Explorer tool, go to **Security & Compliance Center** > **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="d3c4c-133">Standardmäßig gelangen Sie auf der  Seite Schadsoftware, aber verwenden Sie die Dropdownliste Ansicht, um sich mit Ihren Optionen vertraut zu machen. </span><span class="sxs-lookup"><span data-stu-id="d3c4c-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="d3c4c-134">Wenn Sie nach Phish suchen oder in eine Bedrohungskampagne graben, wählen Sie diese Ansichten aus.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-135">![Dropdownansicht im Bedrohungs-Explorer](../../media/threat-explorer-view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-135">![View drop down in Threat Explorer](../../media/threat-explorer-view-drop-down.png)</span></span>

<span data-ttu-id="d3c4c-136">Sobald eine Person für Sicherheitsvorgänge (Sec Ops) die daten auswählt, die sie anzeigen möchten, ob es sich bei dem Bereich um eine schmale Ansicht wie Benutzerübermittlungen oder eine breitere Ansicht wie Alle E-Mails **handelt,** kann sie die Schaltfläche **Absender** verwenden, um weitere Filter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="d3c4c-137">Denken Sie daran, aktualisieren auszuwählen, um die Filteraktionen zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-138">![Schaltfläche "Absender" im Bedrohungs-Explorer](../../media/threat-explorer-sender-button.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-138">![Sender button in Threat Explorer](../../media/threat-explorer-sender-button.png)</span></span>

<span data-ttu-id="d3c4c-139">Das Verfeinern des Fokus in Explorer oder die Echtzeiterkennung kann in Ebenen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="d3c4c-140">Die erste ist **View**.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-140">The first is **View**.</span></span> <span data-ttu-id="d3c4c-141">Die zweite kann als gefilterter *Fokus bezeichnet werden.*</span><span class="sxs-lookup"><span data-stu-id="d3c4c-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="d3c4c-142">Sie können z. B. die Schritte, die Sie bei der Suche nach einer Bedrohung unternommen haben, erneut nachverbilden, indem Sie Ihre Entscheidungen wie die folgende aufzeichnen: Um das Problem im Explorer zu finden, habe ich die Schadsoftwareansicht mit dem Filterfokus Empfänger **ausgewählt.**</span><span class="sxs-lookup"><span data-stu-id="d3c4c-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="d3c4c-143">Dies erleichtert die Nachverarbeitung Ihrer Schritte.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="d3c4c-144">Wenn Sec Ops Tags verwendet, um Konten zu markieren, die sie als besonders geschätzte Ziele betrachten, können sie Auswahlen wie die *Phish-Ansicht* mit einem Tags-Filterfokus treffen (bei Verwendung einen Datumsbereich enthalten). </span><span class="sxs-lookup"><span data-stu-id="d3c4c-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="d3c4c-145">Dies zeigt ihnen alle Phishingversuche, die während eines bestimmten Zeitraums auf ihre hochwertigen Benutzerziele gerichtet sind (z. B. Datumsangaben, an denen bestimmte Phishingangriffe für ihre Branche sehr viel passieren).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="d3c4c-146">Verfeinerungen können für Datumsbereiche mithilfe der Datumsbereichssteuerelemente vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="d3c4c-147">Hier sehen Sie Explorer in **der Ansicht Schadsoftware** mit dem **Filterfokus Erkennungstechnologie.**</span><span class="sxs-lookup"><span data-stu-id="d3c4c-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="d3c4c-148">Es ist jedoch die Schaltfläche **Erweitert,** mit der Sec Ops-Teams tief schweifen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-149">![Erweiterter Filter im Bedrohungs-Explorer](../../media/threat-explorer-advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-149">![Advanced filter in Threat Explorer](../../media/threat-explorer-advanced-filter.png)</span></span>

<span data-ttu-id="d3c4c-150">Wenn Sie auf den **Erweiterten** Filter klicken, wird ein Bereich angezeigt, in dem Sec Ops-Jäger Abfragen selbst erstellen können, damit sie die informationen, die sie sehen müssen, ein- oder ausschließen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="d3c4c-151">Sowohl das Diagramm als auch die Tabelle auf der Explorer-Seite spiegeln ihre Ergebnisse wider.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-152">![Ergebnisse einer Abfrage](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="d3c4c-153">Verwenden Sie **die Schaltfläche** Spaltenoptionen, um die Art von Informationen in der Tabelle zu erhalten, die am hilfreichsten wären:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-154">![Schaltfläche "Spaltenoptionen" hervorgehoben](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-155">![Verfügbare Optionen in Spalten](../../media/threat-explorer-column-options-details.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-155">![Available options in Columns](../../media/threat-explorer-column-options-details.png)</span></span>

<span data-ttu-id="d3c4c-156">Stellen Sie in derselben Mien sicher, dass Sie die Anzeigeoptionen testen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="d3c4c-157">Unterschiedliche Zielgruppen reagieren gut auf unterschiedliche Präsentationen derselben Daten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="d3c4c-158">Für einige Betrachter kann die Karte **"E-Mail-Ursprünge"** zeigen,  dass eine Bedrohung weit verbreitet oder diskreter ist als die Anzeigeoption Kampagnen direkt daneben.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="d3c4c-159">Sec Ops können diese Displays nutzen, um punktet, die die Notwendigkeit von Sicherheit und Schutz unterstreichen, oder für einen späteren Vergleich, um die Effektivität ihrer Aktionen zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-160">![E-Mail-Ursprungskarte](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-161">![Anzeigeoptionen für Kampagnen](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="d3c4c-162">E-Mail-Untersuchung</span><span class="sxs-lookup"><span data-stu-id="d3c4c-162">Email investigation</span></span>

<span data-ttu-id="d3c4c-163">Wenn eine verdächtige E-Mail angezeigt wird, klicken Sie auf den Namen, um das Flyout auf der rechten Seite zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="d3c4c-164">Hier ist das Banner verfügbar, mit dem Sec Ops die [E-Mail-Entitätsseite](mdo-email-entity-page.md) anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="d3c4c-165">Die Seite "E-Mail-Entität" ziehe Inhalte zusammen, die unter **Details**, **Attachments**, **Devices**, gefunden werden können, aber mehr organisierte Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="d3c4c-166">Dazu gehören Z. B. DMARC-Ergebnisse, Nur-Text-Anzeige des E-Mail-Headers mit einer Kopieroption, Verdingungsinformationen zu Anlagen, die sicher detoniert wurden, und Dateien, die diese Detonationen verworfen haben (z. B. IP-Adressen, die kontaktiert wurden, sowie Screenshots von Seiten oder Dateien).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="d3c4c-167">URLs und ihre Urteile werden auch mit ähnlichen Details aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="d3c4c-168">Wenn Sie diese Phase erreichen, ist die E-Mail-Entitätsseite für den letzten Schritt entscheidend:*Korrektur.*</span><span class="sxs-lookup"><span data-stu-id="d3c4c-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-169">![Die Seite "E-Mail-Entität"](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="d3c4c-170">Weitere Informationen zur Seite mit der Rich-E-Mail-Entität (siehe unten auf der Registerkarte Analyse), einschließlich der Ergebnisse von detonierten Anlagen, Erkenntnissen für enthaltene URLs und sicherer E-Mail-Vorschau, klicken Sie [hier](mdo-email-entity-page.md). </span><span class="sxs-lookup"><span data-stu-id="d3c4c-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-171">![Registerkarte "Analyse" der E-Mail-Entitätsseite](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="d3c4c-172">E-Mail-Korrektur</span><span class="sxs-lookup"><span data-stu-id="d3c4c-172">Email remediation</span></span>

<span data-ttu-id="d3c4c-173">Sobald eine Sec Ops-Person feststellt, dass eine E-Mail eine Bedrohung ist, geht es im nächsten Explorer- oder Echtzeiterkennungsschritt um die Bedrohung und deren Behebung.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="d3c4c-174">Dazu kehren Sie zum Bedrohungs-Explorer zurück, aktivieren das Kontrollkästchen für die Problem-E-Mail und verwenden die **Schaltfläche** Aktionen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-175">![Schaltfläche "Aktionen" im Bedrohungs-Explorer](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="d3c4c-176">Hier kann der Analytiker Aktionen wie das Melden der E-Mails als Spam, Phishing oder Schadsoftware, das Kontaktieren von Empfängern oder weitere Untersuchungen durchführen, die das Auslösen automatisierter Untersuchungs- und Reaktionsbücher (oder AIR)-Playbooks (sofern Plan 2 enthalten) umfassen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="d3c4c-177">Oder die E-Mails können auch als "sauber" gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-178">![Die Dropdownliste Aktionen](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="d3c4c-179">Verbesserungen bei der Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="d3c4c-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="d3c4c-180">Warnungs-ID</span><span class="sxs-lookup"><span data-stu-id="d3c4c-180">Alert ID</span></span>

<span data-ttu-id="d3c4c-181">Wenn Sie von einer Warnung in  den Bedrohungs-Explorer navigieren, wird die Ansicht nach Warnungs-ID **gefiltert.**</span><span class="sxs-lookup"><span data-stu-id="d3c4c-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="d3c4c-182">Dies gilt auch für die Echtzeiterkennung.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="d3c4c-183">Nachrichten, die für die jeweilige Warnung relevant sind, und eine E-Mail-Summe (eine Anzahl) werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="d3c4c-184">Sie können sehen, ob eine Nachricht Teil einer Warnung war, und von dieser Nachricht zur zugehörigen Warnung navigieren.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="d3c4c-185">Schließlich ist die Warnungs-ID in der URL enthalten, z. B.: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="d3c4c-185">Finally, alert ID is included in the URL, for example: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-186">![Filtern nach Warnungs-ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-187">![Warnungs-ID im Detailf flyout](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="d3c4c-188">Erweitern der Datenaufbewahrung und des Suchgrenzwerts für Test-Mandanten durch Explorer (und Echtzeiterkennungen)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="d3c4c-189">Im Rahmen dieser Änderung können Analysten E-Mail-Daten innerhalb von 30 Tagen (erhöht von sieben Tagen) im Bedrohungs-Explorer und in Echtzeiterkennungen für Defender für Office P1- und P2-Test-Mandanten suchen und filtern.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="d3c4c-190">Dies wirkt sich nicht auf Produktions mandanten für P1- und P2 E5-Kunden aus, bei denen die Aufbewahrungseinstellung bereits 30 Tage beträgt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="d3c4c-191">Exportgrenzwert aktualisiert</span><span class="sxs-lookup"><span data-stu-id="d3c4c-191">Updated Export limit</span></span> 

<span data-ttu-id="d3c4c-192">Die Anzahl der E-Mail-Datensätze, die aus dem Bedrohungs-Explorer exportiert werden können, beträgt jetzt 200.000 (vor 9990).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="d3c4c-193">Der Satz von Spalten, die exportiert werden können, bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="d3c4c-194">Tags im Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="d3c4c-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="d3c4c-195">Das Feature für Benutzertags befindet sich in der Vorschau und ist möglicherweise nicht für alle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="d3c4c-196">Außerdem können Vorschauen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="d3c4c-197">Informationen zum Veröffentlichungszeitplan finden Sie in der Microsoft 365 Roadmap.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="d3c4c-198">Benutzertags identifizieren bestimmte Benutzergruppen in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d3c4c-199">Weitere Informationen zu Tags, einschließlich Lizenzierung und Konfiguration, finden Sie unter [User tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="d3c4c-200">Im Bedrohungs-Explorer finden Sie Informationen zu Benutzertags in den folgenden Benutzeroberflächen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="d3c4c-201">E-Mail-Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="d3c4c-201">Email grid view</span></span>

<span data-ttu-id="d3c4c-202">Wenn Analysten die Spalte **Tags** im E-Mail-Raster betrachten, werden alle Tags angezeigt, die auf Absender- oder Empfängerpostfächer angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="d3c4c-203">Standardmäßig werden Systemtags wie *Prioritätskonten* zuerst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-204">![Filtern von Tags in der E-Mail-Rasteransicht](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="d3c4c-205">Filtern</span><span class="sxs-lookup"><span data-stu-id="d3c4c-205">Filtering</span></span>

<span data-ttu-id="d3c4c-206">Tags können als Filter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-206">Tags can be used as filters.</span></span> <span data-ttu-id="d3c4c-207">Verwenden Sie auf diese Weise nur die Suche zwischen Prioritätskonten, oder verwenden Sie bestimmte Benutzertagsszenarien.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="d3c4c-208">Sie können auch Ergebnisse mit bestimmten Tags ausschließen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="d3c4c-209">Kombinieren Sie Tags mit anderen Filtern und Datumsbereichen, um Den Untersuchungsbereich zu einenten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="d3c4c-210">[![Filtertags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-211">![Keine Filtertags](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="d3c4c-212">Flyout für E-Mail-Details</span><span class="sxs-lookup"><span data-stu-id="d3c4c-212">Email detail flyout</span></span>

<span data-ttu-id="d3c4c-213">Um die einzelnen Tags für Absender und Empfänger anzuzeigen, wählen Sie eine E-Mail aus, um das Flyout für Nachrichtendetails zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="d3c4c-214">Auf der **Registerkarte Zusammenfassung** werden die Absender- und Empfängertags separat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="d3c4c-215">Die Informationen zu einzelnen Tags für Absender und Empfänger können als CSV-Daten exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-216">![Tags für E-Mail-Details](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="d3c4c-217">Tags-Informationen werden auch im Flyout "URL-Klicks" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="d3c4c-218">Um dies zu sehen, wechseln Sie zur Registerkarte Phish oder Alle E-Mail-> **URLs** oder **URL-Klicks.** Wählen Sie ein einzelnes URL-Flyout aus, um zusätzliche Details zu Klicks für diese URL anzuzeigen, einschließlich aller Tags, die diesem Klick zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="d3c4c-219">Aktualisierte Zeitachsenansicht</span><span class="sxs-lookup"><span data-stu-id="d3c4c-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-220">![URL-Tags](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="d3c4c-221">Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4) ansehen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="d3c4c-222">Erweiterte Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3c4c-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="d3c4c-223">Benutzer mit den meisten Zielbenutzern</span><span class="sxs-lookup"><span data-stu-id="d3c4c-223">Top targeted users</span></span>

<span data-ttu-id="d3c4c-224">Top Malware Families shows the **top targeted users** in the Malware section.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="d3c4c-225">Die Top-Zielbenutzer werden auch über Phish- und Alle E-Mail-Ansichten erweitert.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="d3c4c-226">Analysten können die fünf zielorientierten Benutzer sowie die Anzahl der Versuche für jeden Benutzer in jeder Ansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="d3c4c-227">Sicherheitsvorgänge Personen können die Liste der Zielbenutzer exportieren, bis zu einem Grenzwert von 3.000, zusammen mit der Anzahl der durchgeführten Versuche, für die Offlineanalyse für jede E-Mail-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="d3c4c-228">Wenn Sie außerdem die Anzahl der Versuche auswählen (z. B. 13 Versuche in der abbildung unten), wird eine gefilterte Ansicht im Bedrohungs-Explorer geöffnet, damit Sie weitere Details in E-Mails und Bedrohungen für diesen Benutzer sehen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-229">![Benutzer mit den meisten Zielbenutzern](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="d3c4c-230">Exchange Transportregeln</span><span class="sxs-lookup"><span data-stu-id="d3c4c-230">Exchange transport rules</span></span>

<span data-ttu-id="d3c4c-231">Das Sicherheitsbetriebsteam kann alle Exchange Transportregeln (oder Nachrichtenflussregeln) anzeigen, die auf eine Nachricht angewendet werden, in der Ansicht E-Mail-Raster.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="d3c4c-232">Wählen **Sie spaltenoptionen** im Raster aus, und fügen Sie **dann Exchange Transportregel** in den Spaltenoptionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="d3c4c-233">Die Exchange Transportregeln wird auch im **Flyout Details** in der E-Mail angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="d3c4c-234">Namen und GUIDs der Transportregeln, die auf die Nachricht angewendet werden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="d3c4c-235">Analysten können mithilfe des Namens der Transportregel nach Nachrichten suchen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="d3c4c-236">Dies ist eine CONTAINS-Suche, was bedeutet, dass Sie auch Teilsuchen machen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d3c4c-237">Exchange Die Suche nach Transportregel und die Verfügbarkeit von Namen hängen von der ihnen zugewiesenen rolle ab.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="d3c4c-238">Sie benötigen eine der folgenden Rollen oder Berechtigungen, um die Namen der Transportregel und die Suche anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="d3c4c-239">Auch ohne die folgenden Rollen oder Berechtigungen kann ein Analytiker jedoch die Transportregelbezeichnung und GUID-Informationen in den E-Mail-Details sehen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="d3c4c-240">Andere Aufzeichnungsansichtserfahrungen in E-Mail-Rastern, E-Mail-Flyouts, Filtern und Export sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="d3c4c-241">Exchange Online Nur – Verhinderung von Datenverlust: Alle</span><span class="sxs-lookup"><span data-stu-id="d3c4c-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="d3c4c-242">Exchange Online Only - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="d3c4c-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="d3c4c-243">Microsoft Azure Active Directory oder Exchange Online - Sicherheitsadministrator: Alle</span><span class="sxs-lookup"><span data-stu-id="d3c4c-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="d3c4c-244">Azure Active Directory oder Exchange Online - Security Reader: All</span><span class="sxs-lookup"><span data-stu-id="d3c4c-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="d3c4c-245">Exchange Online Nur - Transportregeln: Alle</span><span class="sxs-lookup"><span data-stu-id="d3c4c-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="d3c4c-246">Exchange Online Only - View-Only Configuration: All</span><span class="sxs-lookup"><span data-stu-id="d3c4c-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="d3c4c-247">Innerhalb des E-Mail-Rasters, des Details-Flyouts und des exportierten CSV erhalten die ETRs eine Name/GUID, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="d3c4c-248">![Exchange Transportregeln](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="d3c4c-249">Eingehende Connectors</span><span class="sxs-lookup"><span data-stu-id="d3c4c-249">Inbound connectors</span></span>

<span data-ttu-id="d3c4c-250">Connectors sind eine Sammlung von Anweisungen, die anpassen, wie Ihre E-Mails zu ihrer Organisation Microsoft 365 oder Office 365 werden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="d3c4c-251">Sie ermöglichen ihnen das Anwenden von Sicherheitseinschränkungen oder -steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="d3c4c-252">Im Bedrohungs-Explorer können Sie die Konnektoren anzeigen, die mit einer E-Mail in Zusammenhang stehen, und mithilfe von Connectornamen nach E-Mails suchen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="d3c4c-253">Die Suche nach Connectors ist eine CONTAINS-Abfrage, was bedeutet, dass teilbegriffssuchen funktionieren können:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c4c-254">![Connectordetails](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="d3c4c-255">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d3c4c-255">Required licenses and permissions</span></span>

<span data-ttu-id="d3c4c-256">Sie müssen [über Microsoft Defender verfügen, Office 365](defender-for-office-365.md) Explorer oder Echtzeiterkennungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="d3c4c-257">Explorer ist in Defender for Office 365 Plan 2 enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="d3c4c-258">Der Bericht "Echtzeiterkennungen" ist in Defender for Office 365 Plan 1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="d3c4c-259">Planen Sie die Zuweisung von Lizenzen für alle Benutzer, die von Defender für alle Benutzer geschützt Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="d3c4c-260">Explorer- und Echtzeiterkennungen zeigen Erkennungsdaten für lizenzierte Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="d3c4c-261">Zum Anzeigen und Verwenden von Explorer- oder Echtzeiterkennungen müssen Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="d3c4c-262">Für das Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-262">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="d3c4c-263">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d3c4c-263">Organization Management</span></span>
  - <span data-ttu-id="d3c4c-264">Sicherheitsadministrator (dies kann im Azure Active Directory Admin Center zugewiesen werden ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="d3c4c-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="d3c4c-265">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="d3c4c-265">Security Reader</span></span>

- <span data-ttu-id="d3c4c-266">Für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-266">For Exchange Online:</span></span>

  - <span data-ttu-id="d3c4c-267">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d3c4c-267">Organization Management</span></span>
  - <span data-ttu-id="d3c4c-268">Organisationsverwaltung – nur Leserechte</span><span class="sxs-lookup"><span data-stu-id="d3c4c-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="d3c4c-269">Schreibgeschützte Empfänger</span><span class="sxs-lookup"><span data-stu-id="d3c4c-269">View-Only Recipients</span></span>
  - <span data-ttu-id="d3c4c-270">Verwaltung der Richtlinientreue</span><span class="sxs-lookup"><span data-stu-id="d3c4c-270">Compliance Management</span></span>

<span data-ttu-id="d3c4c-271">Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="d3c4c-272">Berechtigungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d3c4c-272">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="d3c4c-273">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3c4c-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="d3c4c-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3c4c-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="d3c4c-275">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3c4c-275">More information</span></span>

- [<span data-ttu-id="d3c4c-276">Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden</span><span class="sxs-lookup"><span data-stu-id="d3c4c-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="d3c4c-277">Anzeigen von schädlichen Dateien, die in SharePoint Online, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c4c-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="d3c4c-278">Erhalten Sie eine Übersicht über die Ansichten im Bedrohungs-Explorer (und Echtzeiterkennungen)</span><span class="sxs-lookup"><span data-stu-id="d3c4c-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="d3c4c-279">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="d3c4c-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="d3c4c-280">Automatische Untersuchung und Reaktion in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d3c4c-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="d3c4c-281">Untersuchen von E-Mails mit der Seite "E-Mail-Entität"</span><span class="sxs-lookup"><span data-stu-id="d3c4c-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)