---
title: Kampagnen Ansichten in Office 365 ATP-Plan
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Kampagnenansichten in Office 365 Advanced Threat Protection.
ms.openlocfilehash: df3b3c7a0e8d8f614e5f743b445af07916f1dfd5
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326591"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="88564-103">Kampagnenansichten in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="88564-103">Campaign Views in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="88564-104">Kampagnen Ansichten sind ein Feature in Advanced Threat Protection (ATP) Plan 2 (beispielsweise Microsoft 365 E5 oder Organisationen mit einem ATP Plan 2-Add-on).</span><span class="sxs-lookup"><span data-stu-id="88564-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="88564-105">Kampagnen Ansichten im Security & Compliance Center identifiziert und kategorisiert Phishing-Angriffe im Dienst.</span><span class="sxs-lookup"><span data-stu-id="88564-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="88564-106">Kampagnenansichten können Ihnen bei Folgendem helfen:</span><span class="sxs-lookup"><span data-stu-id="88564-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="88564-107">Phishing-Angriffe effektiv untersuchen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="88564-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="88564-108">Besseres Verständnis des Umfangs des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="88564-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="88564-109">Entscheidungsträgern den Nutzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="88564-109">Show value to decision makers.</span></span>

<span data-ttu-id="88564-110">Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.</span><span class="sxs-lookup"><span data-stu-id="88564-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="88564-111">Was ist eine Kampagne?</span><span class="sxs-lookup"><span data-stu-id="88564-111">What is a campaign?</span></span>

<span data-ttu-id="88564-112">Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen.</span><span class="sxs-lookup"><span data-stu-id="88564-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="88564-113">E-Mail-Angriffe, die Anmeldeinformationen und Unternehmensdaten stehlen, sind eine große und lukrative Branche.</span><span class="sxs-lookup"><span data-stu-id="88564-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="88564-114">Wenn Technologien sich anstrengen, um Angriffe zu stoppen, ändern Angreifer Ihre Methoden, um den weiteren Erfolg sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="88564-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="88564-115">Microsoft nutzt die großen Mengen an Anti-Phishing-, Antispam-und Antischadsoftware-Daten im gesamten Dienst, um Kampagnen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="88564-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="88564-116">Wir analysieren und klassifizieren die Angriffsinformationen anhand verschiedener Faktoren.</span><span class="sxs-lookup"><span data-stu-id="88564-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="88564-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88564-117">For example:</span></span>

- <span data-ttu-id="88564-118">**Angriffsquelle**: die Quell-IP-Adressen und Absender-e-Mail-Domänen.</span><span class="sxs-lookup"><span data-stu-id="88564-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="88564-119">**Nachrichteneigenschaften**: der Inhalt, die Formatvorlage und der Ton der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="88564-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="88564-120">**Nachrichtenempfänger**: wie Empfänger verwandt werden.</span><span class="sxs-lookup"><span data-stu-id="88564-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="88564-121">Beispielsweise Empfängerdomänen, Empfänger Auftrags Funktionen (Administratoren, Führungskräfte usw.), Unternehmenstypen (groß, klein, öffentlich, privat usw.) und Branchen.</span><span class="sxs-lookup"><span data-stu-id="88564-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="88564-122">**Angriffsnutzlast**: böswillige Links, Anlagen oder andere Nutzlasten in den Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="88564-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="88564-123">Eine Kampagne kann von kurzer Dauer sein oder mehrere Tage, Wochen oder Monate mit aktiven und inaktiven Zeitspannen umfassen.</span><span class="sxs-lookup"><span data-stu-id="88564-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="88564-124">Möglicherweise wird eine Kampagne für ihre jeweilige Organisation gestartet, oder Ihre Organisation kann Teil einer größeren Kampagne in mehreren Unternehmen sein.</span><span class="sxs-lookup"><span data-stu-id="88564-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="88564-125">Kampagnen Ansichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="88564-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="88564-126">Kampagnen Ansichten stehen im [Security & Compliance Center](https://protection.office.com) unter **Threat Management** \> **Campaigns**oder direkt unter zur Verfügung <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="88564-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Kampagnenübersicht im Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="88564-128">Sie können auch Kampagnen Ansichten von abrufen:</span><span class="sxs-lookup"><span data-stu-id="88564-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="88564-129">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="88564-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="88564-130">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Alle e-Mails** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="88564-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="88564-131">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Phishing** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="88564-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="88564-132">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Schadsoftware** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="88564-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="88564-133">Um auf Kampagnen Ansichten zuzugreifen, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung**, **Sicherheits Administrator**oder **Sicherheits Leser** im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="88564-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="88564-134">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="88564-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="88564-135">Übersicht über Kampagnen</span><span class="sxs-lookup"><span data-stu-id="88564-135">Campaigns overview</span></span>

<span data-ttu-id="88564-136">Auf der Übersichtsseite werden Informationen zu allen Kampagnen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88564-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="88564-137">Auf der Registerkarte Standard **Kampagne** zeigt der Bereich **Kampagnentyp** ein Balkendiagramm an, in dem die Anzahl der Empfänger pro Tag angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="88564-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="88564-138">Standardmäßig zeigt das Diagramm sowohl **Phishing** -als auch **Schadsoftware** -Daten an.</span><span class="sxs-lookup"><span data-stu-id="88564-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="88564-139">Wenn keine Kampagnendaten angezeigt werden, ändern Sie den Datumsbereich oder die [Filter](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="88564-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="88564-140">Auf der Rest der Übersichtsseite werden auf der Registerkarte **Kampagne** die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="88564-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="88564-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="88564-141">**Name**</span></span>

- <span data-ttu-id="88564-142">**Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="88564-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="88564-143">Beachten Sie, dass alle Nachrichten in der Kampagne nicht unbedingt den gleichen Betreff haben.</span><span class="sxs-lookup"><span data-stu-id="88564-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="88564-144">**Targeted**: der Prozentsatz, der von: (die Anzahl der Kampagnen Empfänger in Ihrer Organisation)/(die Gesamtzahl der Empfänger in der Kampagne für alle Organisationen im Dienst) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="88564-145">Dieser Wert gibt an, in welchem Ausmaß die Kampagne nur an Ihre Organisation (einen höheren Wert) oder an andere Organisationen im Dienst gerichtet wird (ein niedrigerer Wert).</span><span class="sxs-lookup"><span data-stu-id="88564-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="88564-146">**Typ**: dieser Wert ist entweder **Phish** oder **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="88564-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="88564-147">**Untertyp**: dieser Wert enthält weitere Details zur Kampagne.</span><span class="sxs-lookup"><span data-stu-id="88564-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="88564-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88564-148">For example:</span></span>

  - <span data-ttu-id="88564-149">**Phishing**: sofern verfügbar, die Marke, die von dieser Kampagne als Phishing bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="88564-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="88564-150">Beispielsweise,,, `Microsoft` `365` `Unknown` , `Outlook` , oder `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="88564-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="88564-151">**Schadsoftware**: beispielsweise `HTML/PHISH` oder `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="88564-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="88564-152">Sofern verfügbar, die Marke, die von dieser Kampagne als Phishing bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="88564-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="88564-153">Wenn die Erkennung von der ATP-Technologie gesteuert wird, wird das Präfix **ATP-** dem Untertyp Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="88564-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="88564-154">**Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.</span><span class="sxs-lookup"><span data-stu-id="88564-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="88564-155">**Inboxed**: die Anzahl der Benutzer, die Nachrichten von dieser Kampagne in Ihrem Posteingang empfangen haben (nicht an den Junk-e-Mail-Ordner zugestellt).</span><span class="sxs-lookup"><span data-stu-id="88564-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="88564-156">**Geklickt**: die Anzahl der Benutzer, die auf die URL geklickt oder die Anlage in der Phishing-Nachricht geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="88564-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="88564-157">**Klicken Sie auf Rate**: den Prozentsatz,**Clicked**der von "auf  /  **Posteingang**geklickt" berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="88564-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="88564-158">Dieser Wert ist ein Indikator für die Effektivität der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="88564-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="88564-159">Das heißt, wenn die Empfänger die Nachricht als Phishing identifizieren konnten, und wenn Sie nicht auf die Nutzlast-URL klicken.</span><span class="sxs-lookup"><span data-stu-id="88564-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="88564-160">Beachten Sie, dass die **Klick Rate** in Schadsoftware-Kampagnen nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88564-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="88564-161">**Besucht**: Anzahl der Benutzer, die die Nutzlast-Website tatsächlich durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="88564-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="88564-162">Wenn auf Werte **geklickt** wird, aber sichere Links den Zugriff auf die Website blockiert haben, ist dieser Wert gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="88564-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="88564-163">Auf der Registerkarte **Kampagnen Ursprung** werden die Nachrichtenquellen auf einer Weltkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88564-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="88564-164">Filter und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="88564-164">Filters and settings</span></span>

<span data-ttu-id="88564-165">Oben auf der Seite Kampagnen Ansichten stehen verschiedene Filter-und Abfrageeinstellungen zum Auffinden und Isolieren bestimmter Kampagnen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88564-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Kampagnenfilter](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="88564-167">Die einfachste Filterung, die Sie ausführen können, sind Startdatum/-Uhrzeit und Enddatum/-Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="88564-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="88564-168">Wenn Sie die Ansicht weiter filtern möchten, können Sie eine einzelne Eigenschaft mit mehreren Werten filtern, indem Sie auf die Schaltfläche **Kampagnentyp** klicken, Ihre Auswahl treffen und dann auf **Aktualisieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="88564-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="88564-169">Die verfügbaren Kampagneneigenschaften werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="88564-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="88564-170">Standard</span><span class="sxs-lookup"><span data-stu-id="88564-170">Basic</span></span>

  - <span data-ttu-id="88564-171">**Kampagnentyp**: Wählen Sie **Schadsoftware** oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="88564-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="88564-172">Das Löschen der Auswahl hat das gleiche Ergebnis wie das auswählen beider Elemente.</span><span class="sxs-lookup"><span data-stu-id="88564-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="88564-173">**Name der Kampagne**</span><span class="sxs-lookup"><span data-stu-id="88564-173">**Campaign name**</span></span>
  - <span data-ttu-id="88564-174">**Kampagnen Untertyp**</span><span class="sxs-lookup"><span data-stu-id="88564-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="88564-175">**Sender**</span><span class="sxs-lookup"><span data-stu-id="88564-175">**Sender**</span></span>
  - <span data-ttu-id="88564-176">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="88564-176">**Recipients**</span></span>
  - <span data-ttu-id="88564-177">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="88564-177">**Sender domain**</span></span>
  - <span data-ttu-id="88564-178">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="88564-178">**Subject**</span></span>
  - <span data-ttu-id="88564-179">**Dateiname der Anlage**</span><span class="sxs-lookup"><span data-stu-id="88564-179">**Attachment filename**</span></span>
  - <span data-ttu-id="88564-180">**Schadsoftware-Familie**</span><span class="sxs-lookup"><span data-stu-id="88564-180">**Malware family**</span></span>
  - <span data-ttu-id="88564-181">**Zustellungs Aktion**</span><span class="sxs-lookup"><span data-stu-id="88564-181">**Delivery action**</span></span>
  - <span data-ttu-id="88564-182">**Erkennungstechnologie**</span><span class="sxs-lookup"><span data-stu-id="88564-182">**Detection technology**</span></span>
  - <span data-ttu-id="88564-183">**Tags**</span><span class="sxs-lookup"><span data-stu-id="88564-183">**Tags**</span></span>
  - <span data-ttu-id="88564-184">**System Überschreibungen**</span><span class="sxs-lookup"><span data-stu-id="88564-184">**System overrides**</span></span>

- <span data-ttu-id="88564-185">Erweitert</span><span class="sxs-lookup"><span data-stu-id="88564-185">Advanced</span></span>

  - <span data-ttu-id="88564-186">**Internet Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf.</span><span class="sxs-lookup"><span data-stu-id="88564-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="88564-187">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="88564-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="88564-188">**Netzwerknachrichten-ID**: ein GUID-Wert, der im Headerfeld **X-MS-Exchange-Organization-Network-Message-ID** im Nachrichtenkopf verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="88564-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="88564-189">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="88564-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="88564-190">**Attachment SHA256**: um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="88564-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="88564-191">**Cluster-ID**</span><span class="sxs-lookup"><span data-stu-id="88564-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="88564-192">**Warnungsrichtlinien-ID**</span><span class="sxs-lookup"><span data-stu-id="88564-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="88564-193">URLs</span><span class="sxs-lookup"><span data-stu-id="88564-193">URLs</span></span>

  - <span data-ttu-id="88564-194">**URL-Domäne**</span><span class="sxs-lookup"><span data-stu-id="88564-194">**URL domain**</span></span>
  - <span data-ttu-id="88564-195">**URL-Domäne und Pfad**</span><span class="sxs-lookup"><span data-stu-id="88564-195">**URL domain and path**</span></span>
  - <span data-ttu-id="88564-196">**URL**</span><span class="sxs-lookup"><span data-stu-id="88564-196">**URL**</span></span>
  - <span data-ttu-id="88564-197">**URL-Pfad**</span><span class="sxs-lookup"><span data-stu-id="88564-197">**URL path**</span></span>
  - <span data-ttu-id="88564-198">**Klicken Sie auf Urteil**</span><span class="sxs-lookup"><span data-stu-id="88564-198">**Click verdict**</span></span>

<span data-ttu-id="88564-199">Für eine erweiterte Filterung, einschließlich der Filterung durch mehrere Eigenschaften, können Sie auf die Schaltfläche **Erweiterter Filter** klicken, um eine Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88564-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="88564-200">Die gleichen Kampagneneigenschaften sind verfügbar, jedoch mit den folgenden Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="88564-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="88564-201">Sie können auf **Bedingung hinzufügen** klicken, um mehrere Bedingungen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="88564-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="88564-202">Sie können zwischen Bedingungen den **und-oder-** **Operator auswählen** .</span><span class="sxs-lookup"><span data-stu-id="88564-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="88564-203">Sie können das Element **Bedingungsgruppe** unten in der Liste Bedingungen auswählen, um komplexe zusammengesetzte Bedingungen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="88564-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="88564-204">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="88564-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="88564-205">Nachdem Sie einen einfachen oder erweiterten Filter erstellt haben, können Sie ihn speichern, indem Sie **Abfrage speichern** oder **Abfrage speichern**unter verwenden.</span><span class="sxs-lookup"><span data-stu-id="88564-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="88564-206">Wenn Sie später zu Kampagnen Ansichten zurückkehren, können Sie einen gespeicherten Filter laden, indem Sie auf **gespeicherte Abfrageeinstellungen**klicken.</span><span class="sxs-lookup"><span data-stu-id="88564-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="88564-207">Klicken Sie zum Exportieren des Diagramms oder der Kampagnenliste auf **exportieren** , und wählen Sie **Diagrammdaten exportieren** oder **Kampagnenliste**exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="88564-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="88564-208">Wenn Sie über ein Microsoft Defender ATP-Abonnement verfügen, können Sie auf **WDATP** klicken, um die Kampagneninformationen mit Microsoft Defender ATP zu verbinden oder zu trennen.</span><span class="sxs-lookup"><span data-stu-id="88564-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="88564-209">Weitere Informationen finden Sie unter [integrieren Office 365 ATP mit Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="88564-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="88564-210">Kampagnendetails</span><span class="sxs-lookup"><span data-stu-id="88564-210">Campaign details</span></span>

<span data-ttu-id="88564-211">Wenn Sie auf den Namen einer Kampagne klicken, werden die kampagnendetails in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88564-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="88564-212">Kampagneninformationen</span><span class="sxs-lookup"><span data-stu-id="88564-212">Campaign information</span></span>

<span data-ttu-id="88564-213">Oben in der Ansicht kampagnendetails stehen die folgenden Kampagneninformationen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="88564-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="88564-214">**ID**: der eindeutige Kampagnen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="88564-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="88564-215">**Anfang und Ende** **: Startdatum und**Enddatum der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="88564-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="88564-216">Beachten Sie, dass sich diese Datumsangaben möglicherweise weiter ausdehnen als die Filterdaten, die Sie auf der Übersichtsseite ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="88564-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="88564-217">**Symptom**: Dieser Abschnitt enthält die folgenden Daten für den ausgewählten Datumsbereichsfilter (oder den Sie in der Zeitachse auswählen):</span><span class="sxs-lookup"><span data-stu-id="88564-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="88564-218">Die Gesamtzahl der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="88564-218">The total number of recipients.</span></span>
  - <span data-ttu-id="88564-219">Die Anzahl der Nachrichten, die "Posteingang" (also im Posteingang, nicht an den Junk-e-Mail-Ordner) gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="88564-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="88564-220">Wie viele Benutzer auf die URL-Nutzlast in der Phishing-Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="88564-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="88564-221">Howe viele Benutzer haben die URL besucht.</span><span class="sxs-lookup"><span data-stu-id="88564-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="88564-222">**Targeted**: der Prozentsatz, der von: (die Anzahl der Kampagnen Empfänger in Ihrer Organisation)/(die Gesamtzahl der Empfänger in der Kampagne für alle Organisationen im Dienst) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="88564-223">Beachten Sie, dass dieser Wert über die gesamte Lebensdauer der Kampagne berechnet wird und nicht basierend auf den Datums Filtern geändert wird.</span><span class="sxs-lookup"><span data-stu-id="88564-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="88564-224">Eine interaktive Zeitachse der Kampagnenaktivität: die Zeitachse zeigt die Aktivität während der gesamten Lebensdauer der Kampagne an.</span><span class="sxs-lookup"><span data-stu-id="88564-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="88564-225">Standardmäßig enthält der schattierte Bereich den Datumsbereichsfilter, den Sie in der Übersicht ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="88564-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="88564-226">Sie können durch Klicken und ziehen einen bestimmten Startpunkt und Endpunkt auswählen, um <u>die Daten zu ändern, die im **IMPACT** -Bereich angezeigt werden, und auf den Rest der Seite, wie in den nächsten Abschnitten beschrieben</u>.</span><span class="sxs-lookup"><span data-stu-id="88564-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="88564-227">In der Titelleiste können Sie auf die Schaltfläche Download Campaign Write- **up** klicken, ![ ](../../media/download-campaign-write-up-button.png) um die kampagnendetails in ein Word-Dokument (standardmäßig mit dem Namen "CampaignReport.docx") herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="88564-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="88564-228">Beachten Sie, dass der Download Details über die gesamte Lebensdauer der Kampagne enthält (nicht nur die Filterdaten, die Sie ausgewählt haben).</span><span class="sxs-lookup"><span data-stu-id="88564-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Kampagneninformationen](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="88564-230">Kampagnenfluss</span><span class="sxs-lookup"><span data-stu-id="88564-230">Campaign flow</span></span>

<span data-ttu-id="88564-231">In der Mitte der Ansicht kampagnendetails werden wichtige Details zur Kampagne im Abschnitt **Flow** in einem horizontalen Flussdiagramm (als _Sankey_ -Diagramm bezeichnet) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="88564-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="88564-232">Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="88564-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="88564-233">Die Informationen, die im **Fluss** Diagramm angezeigt werden, werden wie im vorherigen Abschnitt beschrieben durch den schattierten Datumsbereich in der Zeitachse gesteuert.</span><span class="sxs-lookup"><span data-stu-id="88564-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="88564-235">Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).</span><span class="sxs-lookup"><span data-stu-id="88564-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="88564-236">Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="88564-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="88564-237">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="88564-237">**Sender IPs**</span></span>

- <span data-ttu-id="88564-238">**Absenderdomänen**</span><span class="sxs-lookup"><span data-stu-id="88564-238">**Sender domains**</span></span>

- <span data-ttu-id="88564-239">**Filter Urteile**: Urteils Werte beziehen sich auf die verfügbaren Phishing-und Spamfilter Urteile, wie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="88564-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="88564-240">Die verfügbaren Werte werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="88564-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="88564-241">Wert</span><span class="sxs-lookup"><span data-stu-id="88564-241">Value</span></span>|<span data-ttu-id="88564-242">Spam Filter Urteil</span><span class="sxs-lookup"><span data-stu-id="88564-242">Spam filter verdict</span></span>|<span data-ttu-id="88564-243">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88564-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="88564-244">**Zulässig**</span><span class="sxs-lookup"><span data-stu-id="88564-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="88564-245">Die Nachricht wurde vor der Auswertung durch Spamfilterung als nicht-Spam-und/oder übersprungene Filterung markiert.</span><span class="sxs-lookup"><span data-stu-id="88564-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="88564-246">Beispielsweise wurde die Nachricht von einer e-Mail-Fluss Regel (auch als Transportregel bezeichnet) als nicht Spam gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="88564-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="88564-247">Die Nachricht hat aus anderen Gründen die Spamfilterung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="88564-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="88564-248">Beispielsweise scheint sich der Absender und der Empfänger in derselben Organisation zu befinden.</span><span class="sxs-lookup"><span data-stu-id="88564-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="88564-249">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="88564-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="88564-250">Die Nachricht wurde als Spam markiert, bevor Sie von der Spamfilterung ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="88564-251">Beispielsweisedurch eine Nachrichtenfluss Regel.</span><span class="sxs-lookup"><span data-stu-id="88564-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="88564-252">**Erkannt**</span><span class="sxs-lookup"><span data-stu-id="88564-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="88564-253">Die Nachricht wurde vom Spamfilter als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="88564-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="88564-254">**Nicht erkannt**</span><span class="sxs-lookup"><span data-stu-id="88564-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="88564-255">Die Nachricht wurde durch Spamfilterung als nicht Spam gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="88564-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="88564-256">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="88564-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="88564-257">Die Nachricht hat die Spamfilterung übersprungen, da Sie aus der Quarantäne freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="88564-258">**Mandanten zulässig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="88564-259">Die Nachricht hat die Spamfilterung aufgrund der Einstellungen in einer Anti-Spam-Richtlinie übersprungen.</span><span class="sxs-lookup"><span data-stu-id="88564-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="88564-260">Beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassene Domäne.</span><span class="sxs-lookup"><span data-stu-id="88564-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="88564-261">**Mandanten Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="88564-262">Die Nachricht wurde aufgrund der Einstellungen in einer Anti-Spam-Richtlinie durch Spamfilterung blockiert.</span><span class="sxs-lookup"><span data-stu-id="88564-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="88564-263">Beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassene Domäne.</span><span class="sxs-lookup"><span data-stu-id="88564-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="88564-264">**Benutzer zulassen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="88564-265">Die Nachricht hat die Spamfilterung übersprungen, da sich der Absender in der Liste sicherer Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="88564-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="88564-266">**Benutzer Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="88564-267">Die Nachricht wurde durch die Spamfilterung blockiert, da sich der Absender in der Liste Blockierte Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="88564-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="88564-268">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="88564-268">**ZAP**</span></span>|<span data-ttu-id="88564-269">n/v</span><span class="sxs-lookup"><span data-stu-id="88564-269">n/a</span></span>|<span data-ttu-id="88564-270">[Zero-Hour Auto Purge (zap)](zero-hour-auto-purge.md) hat die zugestellte Nachricht in den Junk-e-Mail-Ordner oder in die Quarantäne verschoben.</span><span class="sxs-lookup"><span data-stu-id="88564-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="88564-271">Sie konfigurieren die Aktion in ihrer Anti-Spam-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="88564-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="88564-272"><sup>\*</sup> Überprüfen Sie Ihre Anti-Spam-Richtlinien, da die zulässige Nachricht wahrscheinlich vom Dienst blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="88564-273"><sup>\*\*</sup> Überprüfen Sie Ihre Anti-Spam-Richtlinien, da diese Nachrichten isoliert und nicht zugestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88564-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="88564-274">**Zustellungsorte**: Sie möchten wahrscheinlich Nachrichten untersuchen, die an Empfänger gesendet wurden (entweder an den Posteingang oder den Junk-e-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht klicken.</span><span class="sxs-lookup"><span data-stu-id="88564-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="88564-275">Sie können auch die isolierten Nachrichten aus der Quarantäne entfernen.</span><span class="sxs-lookup"><span data-stu-id="88564-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="88564-276">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="88564-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="88564-277">**Ordner gelöscht**</span><span class="sxs-lookup"><span data-stu-id="88564-277">**Deleted folder**</span></span>
  - <span data-ttu-id="88564-278">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="88564-278">**Dropped**</span></span>
  - <span data-ttu-id="88564-279">**Extern**: der Empfänger befindet sich in Ihrer lokalen e-Mail-Organisation in Hybrid Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="88564-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="88564-280">**Fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="88564-280">**Failed**</span></span>
  - <span data-ttu-id="88564-281">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="88564-281">**Forwarded**</span></span>
  - <span data-ttu-id="88564-282">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="88564-282">**Inbox**</span></span>
  - <span data-ttu-id="88564-283">**Junk-E-Mail-Ordner**</span><span class="sxs-lookup"><span data-stu-id="88564-283">**Junk folder**</span></span>
  - <span data-ttu-id="88564-284">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="88564-284">**Quarantine**</span></span>
  - <span data-ttu-id="88564-285">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="88564-285">**Unknown**</span></span>

- <span data-ttu-id="88564-286">**URL-Klicks**: diese Werte werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="88564-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="88564-287">In allen Ebenen, die mehr als 10 Elemente enthalten, werden die oberen 10 Elemente angezeigt, während der Rest in **anderen**zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="88564-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="88564-288">URL-Klicks</span><span class="sxs-lookup"><span data-stu-id="88564-288">URL clicks</span></span>

<span data-ttu-id="88564-289">Wenn eine Phishing-Nachricht an den Posteingang des Empfängers oder den Junk-e-Mail-Ordner gesendet wird, besteht immer die Möglichkeit, dass der Benutzer auf die Nutzlast-URL klickt.</span><span class="sxs-lookup"><span data-stu-id="88564-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="88564-290">Wenn Sie nicht auf die URL klicken, ist dies ein kleines Maß an Erfolg, aber Sie müssen ermitteln, warum die Phishing-Nachricht sogar an das Postfach übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="88564-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="88564-291">Wenn ein Benutzer in der Phishing-Nachricht auf die Nutzlast-URL geklickt hat, werden die Aktionen im Bereich **URL Klicks** des Diagramms in der Ansicht kampagnendetails angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88564-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="88564-292">**Zulässig**</span><span class="sxs-lookup"><span data-stu-id="88564-292">**Allowed**</span></span>

- <span data-ttu-id="88564-293">**BlockPage**: der Empfänger hat auf die Nutzlast-URL geklickt, aber der Zugriff auf die bösartige Website wurde durch eine Richtlinie zu [sicheren Links](atp-safe-links.md) in Ihrer Organisation blockiert.</span><span class="sxs-lookup"><span data-stu-id="88564-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>

- <span data-ttu-id="88564-294">**BlockPageOverride**: der Empfänger hat auf die Nutzlast-URL in der Nachricht geklickt, sichere Links haben versucht, diese zu beenden, aber Sie durften den Block außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="88564-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="88564-295">Überprüfen Sie Ihre [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) , um zu erfahren, warum Benutzer das Urteil "sichere Links" außer Kraft setzen und mit der bösartigen Website fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="88564-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="88564-296">**PendingDetonationPage**: sichere Anlagen in Office 365 ATP wird gerade dabei sein, die Nutzlast-URL in einer virtuellen Computerumgebung zu öffnen und zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="88564-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="88564-297">**PendingDetonationPageOverride**: der Empfänger durfte den detonations Prozess für die Nutzlast außer Kraft setzen und die URL öffnen, ohne auf die Ergebnisse zu warten.</span><span class="sxs-lookup"><span data-stu-id="88564-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="88564-298">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="88564-298">Tabs</span></span>

<span data-ttu-id="88564-299">Auf den Registerkarten in der Ansicht kampagnendetails können Sie die Kampagne weiter untersuchen.</span><span class="sxs-lookup"><span data-stu-id="88564-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="88564-300">Die Informationen, die auf den Registerkarten angezeigt werden, werden durch den schattierten Datumsbereich in der Zeitleiste gesteuert, wie im Abschnitt [Kampagneninformationen](#campaign-information) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="88564-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="88564-301">**URL Klicks**: Wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben, ist dieser Abschnitt leer.</span><span class="sxs-lookup"><span data-stu-id="88564-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="88564-302">Wenn ein Benutzer auf die URL klicken konnte, werden die folgenden Werte aufgefüllt:</span><span class="sxs-lookup"><span data-stu-id="88564-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="88564-303">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="88564-304">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="88564-305">**Klicken Sie auf Zeit**</span><span class="sxs-lookup"><span data-stu-id="88564-305">**Click time**</span></span>
  - <span data-ttu-id="88564-306">**Klicken Sie auf Urteil**</span><span class="sxs-lookup"><span data-stu-id="88564-306">**Click verdict**</span></span>

- <span data-ttu-id="88564-307">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="88564-307">**Sender IPs**</span></span>

  - <span data-ttu-id="88564-308">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="88564-309">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="88564-309">**Total count**</span></span>
  - <span data-ttu-id="88564-310">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="88564-310">**Inboxed**</span></span>
  - <span data-ttu-id="88564-311">**Nicht Posteingang**</span><span class="sxs-lookup"><span data-stu-id="88564-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="88564-312">**Weitergegebene SPF**: der Absender wurde vom [SPF (Sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="88564-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="88564-313">Ein Absender, der die SPF-Überprüfung nicht übergibt, gibt einen nicht authentifizierten Absender an, oder die Nachricht fälscht einen legitimen Absender.</span><span class="sxs-lookup"><span data-stu-id="88564-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="88564-314">**Absender**</span><span class="sxs-lookup"><span data-stu-id="88564-314">**Senders**</span></span>

  - <span data-ttu-id="88564-315">**Absender**: Dies ist die tatsächliche Absenderadresse im SMTP-Mail von-Befehl, die nicht unbedingt die von:-e-Mail-Adresse ist, die Benutzern in Ihren e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="88564-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="88564-316">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="88564-316">**Total count**</span></span>
  - <span data-ttu-id="88564-317">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="88564-317">**Inboxed**</span></span>
  - <span data-ttu-id="88564-318">**Nicht Posteingang**</span><span class="sxs-lookup"><span data-stu-id="88564-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="88564-319">**DKIM-Übergabe**: der Absender wurde durch Domänenschlüssel authentifiziert, die [Mail (DKIM) identifiziert](support-for-validation-of-dkim-signed-messages.md)haben.</span><span class="sxs-lookup"><span data-stu-id="88564-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="88564-320">Ein Absender, der die DKIM-Überprüfung nicht übergibt, gibt einen nicht authentifizierten Absender an, oder die Nachricht fälscht einen legitimen Absender.</span><span class="sxs-lookup"><span data-stu-id="88564-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="88564-321">**DMARC wurde übergeben**: der Absender wurde durch [domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität authentifiziert (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="88564-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="88564-322">Ein Absender, der die DMARC-Überprüfung nicht übergibt, gibt einen nicht authentifizierten Absender an, oder die Nachricht fälscht einen legitimen Absender.</span><span class="sxs-lookup"><span data-stu-id="88564-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="88564-323">**Anlagen**</span><span class="sxs-lookup"><span data-stu-id="88564-323">**Attachments**</span></span>

  - <span data-ttu-id="88564-324">**Filename**</span><span class="sxs-lookup"><span data-stu-id="88564-324">**Filename**</span></span>
  - <span data-ttu-id="88564-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="88564-325">**SHA256**</span></span>
  - <span data-ttu-id="88564-326">**Schadsoftware-Familie**</span><span class="sxs-lookup"><span data-stu-id="88564-326">**Malware family**</span></span>
  - <span data-ttu-id="88564-327">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="88564-327">**Total count**</span></span>

- <span data-ttu-id="88564-328">**URL**</span><span class="sxs-lookup"><span data-stu-id="88564-328">**URL**</span></span>

  - <span data-ttu-id="88564-329">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88564-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="88564-330">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="88564-330">**Total Count**</span></span>

<span data-ttu-id="88564-331"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält.</span><span class="sxs-lookup"><span data-stu-id="88564-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="88564-332">Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="88564-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="88564-333">Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="88564-333">Buttons</span></span>

<span data-ttu-id="88564-334">Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="88564-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="88564-335">**Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="88564-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="88564-336">Untersuchen von **Nachrichten im Posteingang**: öffnet eine neue Suchregisterkarte "Threat Explorer" mithilfe der **Kampagnen-ID** und des **Zustellungs Speicherorts: Posteingang** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="88564-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
