---
title: Kampagnen Ansichten in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Kampagnenansichten in Office 365 Advanced Threat Protection.
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039453"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="dfe64-103">Kampagnen Ansichten in ATP</span><span class="sxs-lookup"><span data-stu-id="dfe64-103">Campaign Views in ATP</span></span>

<span data-ttu-id="dfe64-104">Kampagnen Ansichten sind ein Feature in Advanced Threat Protection (ATP) im Security & Compliance Center, das Phishing-Angriffe im Dienst identifiziert und kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="dfe64-105">Kampagnenansichten können Ihnen bei Folgendem helfen:</span><span class="sxs-lookup"><span data-stu-id="dfe64-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="dfe64-106">Phishing-Angriffe effektiv untersuchen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="dfe64-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="dfe64-107">Besseres Verständnis des Umfangs des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="dfe64-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="dfe64-108">Entscheidungsträgern den Nutzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-108">Show value to decision makers.</span></span>

<span data-ttu-id="dfe64-109">Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.</span><span class="sxs-lookup"><span data-stu-id="dfe64-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="dfe64-110">Was ist eine Kampagne?</span><span class="sxs-lookup"><span data-stu-id="dfe64-110">What is a campaign?</span></span>

<span data-ttu-id="dfe64-111">Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="dfe64-112">E-Mail-Angriffe, die Anmeldeinformationen und Unternehmensdaten stehlen, sind eine große und lukrative Branche.</span><span class="sxs-lookup"><span data-stu-id="dfe64-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="dfe64-113">Wenn Technologien sich anstrengen, um Angriffe zu stoppen, ändern Angreifer Ihre Methoden, um den weiteren Erfolg sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="dfe64-114">Microsoft nutzt die großen Mengen an Anti-Phishing-, Antispam-und Antischadsoftware-Daten im gesamten Dienst, um Kampagnen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dfe64-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="dfe64-115">Wir analysieren und klassifizieren die Angriffsinformationen anhand verschiedener Faktoren.</span><span class="sxs-lookup"><span data-stu-id="dfe64-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="dfe64-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dfe64-116">For example:</span></span>

- <span data-ttu-id="dfe64-117">**Angriffsquelle**: die Quell-IP-Adressen und Absender-e-Mail-Domänen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="dfe64-118">**Eigenschaften von Angriffs Nachrichten**: der Inhalt, die Formatvorlage und der Ton der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="dfe64-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="dfe64-119">**Angriffsempfänger**: Empfängerdomänen, Aufgaben des Empfängers (Administratoren, Führungskräfte usw.), Firmentypen (groß, klein, öffentlich, privat usw.) und Branchen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="dfe64-120">**Angriffsnutzlast**: böswillige Links, Anlagen oder andere Nutzlasten in den Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="dfe64-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="dfe64-121">Eine Kampagne kann von kurzer Dauer sein oder mehrere Tage, Wochen oder Monate mit aktiven und inaktiven Zeitspannen umfassen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="dfe64-122">Möglicherweise wird eine Kampagne für ihre jeweilige Organisation gestartet, oder Ihre Organisation kann Teil einer größeren Kampagne in mehreren Unternehmen sein.</span><span class="sxs-lookup"><span data-stu-id="dfe64-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="dfe64-123">Kampagnen Ansichten das Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dfe64-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="dfe64-124">Kampagnen Ansichten stehen im [Security & Compliance Center](https://protection.office.com) unter **Threat Management** \> **Campaigns**oder direkt unter zur Verfügung <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="dfe64-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Kampagnenübersicht im Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="dfe64-126">Sie können auch Kampagnen Ansichten von abrufen:</span><span class="sxs-lookup"><span data-stu-id="dfe64-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="dfe64-127">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="dfe64-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="dfe64-128">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Alle e-Mails** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="dfe64-129">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Phishing** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="dfe64-130">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Schadsoftware** \> Registerkarte **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="dfe64-131">Um auf Kampagnen Ansichten zuzugreifen, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung**, **Sicherheits Administrator**oder **Sicherheits Leser** im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="dfe64-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="dfe64-132">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dfe64-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="dfe64-133">Übersicht über Kampagnen</span><span class="sxs-lookup"><span data-stu-id="dfe64-133">Campaigns overview</span></span>

<span data-ttu-id="dfe64-134">Auf der Übersichtsseite werden Informationen zu allen Kampagnen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="dfe64-135">Auf der Registerkarte Standard **Kampagne** zeigt der Bereich **Kampagnentyp** ein Balkendiagramm an, in dem die Anzahl der Empfänger pro Tag angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="dfe64-136">Standardmäßig zeigt das Diagramm sowohl **Phishing** -als auch **Schadsoftware** -Daten an.</span><span class="sxs-lookup"><span data-stu-id="dfe64-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="dfe64-137">Wenn keine Kampagnendaten angezeigt werden, ändern Sie den Datumsbereich oder die [Filter](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="dfe64-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="dfe64-138">Auf der Rest der Übersichtsseite werden auf der Registerkarte **Kampagne** die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dfe64-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="dfe64-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="dfe64-139">**Name**</span></span>

- <span data-ttu-id="dfe64-140">**Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="dfe64-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="dfe64-141">Beachten Sie, dass alle Nachrichten in der Kampagne nicht unbedingt den gleichen Betreff haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="dfe64-142">**Targeted**: der Prozentsatz, der von: (die Anzahl der Kampagnen Empfänger in Ihrer Organisation)/(die Gesamtzahl der Empfänger in der Kampagne für alle Organisationen im Dienst) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="dfe64-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="dfe64-143">Dieser Wert gibt an, in welchem Ausmaß die Kampagne speziell an Ihre Organisation (einen höheren Wert) oder an andere Organisationen im Dienst gerichtet ist (ein niedrigerer Wert).</span><span class="sxs-lookup"><span data-stu-id="dfe64-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="dfe64-144">**Typ**: dieser Wert ist entweder **Phish** oder **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="dfe64-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="dfe64-145">**Untertyp**: dieser Wert enthält weitere Details zur Kampagne.</span><span class="sxs-lookup"><span data-stu-id="dfe64-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="dfe64-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dfe64-146">For example:</span></span>

  - <span data-ttu-id="dfe64-147">**Phishing**: sofern verfügbar, die Marke, die von dieser Kampagne als Phishing bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="dfe64-148">Beispielsweise,,, `Microsoft` `365` `Unknown` , `Outlook` , oder `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="dfe64-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="dfe64-149">**Schadsoftware**: beispielsweise `HTML/PHISH` oder `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="dfe64-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="dfe64-150">Sofern verfügbar, die Marke, die von dieser Kampagne als Phishing bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="dfe64-151">Wenn die Erkennung von der ATP-Technologie gesteuert wird, wird das Präfix **ATP-** dem Untertyp Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="dfe64-152">**Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="dfe64-153">**Inboxed**: die Anzahl der Benutzer, die Nachrichten von dieser Kampagne in Ihrem Posteingang empfangen haben (nicht an den Junk-e-Mail-Ordner zugestellt).</span><span class="sxs-lookup"><span data-stu-id="dfe64-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="dfe64-154">**Geklickt**: die Anzahl der Benutzer, die auf die URL geklickt oder die Anlage in der Phishing-Nachricht geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="dfe64-155">**Klicken Sie auf Rate**: den Prozentsatz,**Clicked**der von "auf  /  **Posteingang**geklickt" berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="dfe64-156">Dieser Wert ist ein Indikator für die Effektivität der Kampagne und gibt an, ob die Empfänger die Nachricht als Phishing identifizieren konnten, und vermeiden Sie das Klicken auf die Nutzlast-URL.</span><span class="sxs-lookup"><span data-stu-id="dfe64-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="dfe64-157">Beachten Sie, dass dieser Wert in Schadsoftware-Kampagnen nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="dfe64-158">**Besucht**: Anzahl der Benutzer, die die Nutzlast-Website tatsächlich durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="dfe64-159">Wenn auf Werte **geklickt** wird, aber sichere Links den Zugriff auf die Website blockiert haben, ist dieser Wert gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="dfe64-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="dfe64-160">Auf der Registerkarte **Kampagnen Ursprung** werden die Nachrichtenquellen auf einer Weltkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="dfe64-161">Filter und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="dfe64-161">Filters and settings</span></span>

<span data-ttu-id="dfe64-162">Oben auf der Seite Kampagnen Ansichten stehen verschiedene Filter-und Abfrageeinstellungen zum Auffinden und Isolieren bestimmter Kampagnen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="dfe64-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Kampagnenfilter](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="dfe64-164">Die einfachste Filterung, die Sie ausführen können, sind Startdatum/-Uhrzeit und Enddatum/-Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="dfe64-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="dfe64-165">Wenn Sie die Ansicht weiter filtern möchten, können Sie eine einzelne Eigenschaft mit mehreren Werten filtern, indem Sie auf die Schaltfläche **Kampagnentyp** klicken, Ihre Auswahl treffen und dann auf **Aktualisieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="dfe64-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="dfe64-166">Die verfügbaren Kampagneneigenschaften werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="dfe64-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="dfe64-167">Basic</span><span class="sxs-lookup"><span data-stu-id="dfe64-167">Basic</span></span>

  - <span data-ttu-id="dfe64-168">**Kampagnentyp**: Wählen Sie **Schadsoftware** oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="dfe64-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="dfe64-169">Das Löschen der Auswahl hat das gleiche Ergebnis wie das auswählen beider Elemente.</span><span class="sxs-lookup"><span data-stu-id="dfe64-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="dfe64-170">**Name der Kampagne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-170">**Campaign name**</span></span>
  - <span data-ttu-id="dfe64-171">**Kampagnen Untertyp**</span><span class="sxs-lookup"><span data-stu-id="dfe64-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="dfe64-172">**Sender**</span><span class="sxs-lookup"><span data-stu-id="dfe64-172">**Sender**</span></span>
  - <span data-ttu-id="dfe64-173">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="dfe64-173">**Recipients**</span></span>
  - <span data-ttu-id="dfe64-174">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-174">**Sender domain**</span></span>
  - <span data-ttu-id="dfe64-175">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="dfe64-175">**Subject**</span></span>
  - <span data-ttu-id="dfe64-176">**Dateiname der Anlage**</span><span class="sxs-lookup"><span data-stu-id="dfe64-176">**Attachment filename**</span></span>
  - <span data-ttu-id="dfe64-177">**Schadsoftware-Familie**</span><span class="sxs-lookup"><span data-stu-id="dfe64-177">**Malware family**</span></span>
  - <span data-ttu-id="dfe64-178">**Zustellungs Aktion**</span><span class="sxs-lookup"><span data-stu-id="dfe64-178">**Delivery action**</span></span>
  - <span data-ttu-id="dfe64-179">**Erkennungstechnologie**</span><span class="sxs-lookup"><span data-stu-id="dfe64-179">**Detection technology**</span></span>
  - <span data-ttu-id="dfe64-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="dfe64-180">**Tags**</span></span>
  - <span data-ttu-id="dfe64-181">**System Überschreibungen**</span><span class="sxs-lookup"><span data-stu-id="dfe64-181">**System overrides**</span></span>

- <span data-ttu-id="dfe64-182">Fortgeschritten</span><span class="sxs-lookup"><span data-stu-id="dfe64-182">Advanced</span></span>

  - <span data-ttu-id="dfe64-183">**Internet Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf.</span><span class="sxs-lookup"><span data-stu-id="dfe64-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="dfe64-184">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="dfe64-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="dfe64-185">**Netzwerknachrichten-ID**: ein GUID-Wert, der im Headerfeld **X-MS-Exchange-Organization-Network-Message-ID** im Nachrichtenkopf verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dfe64-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="dfe64-186">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="dfe64-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="dfe64-187">**Attachment SHA256**: um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="dfe64-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="dfe64-188">**Cluster-ID**</span><span class="sxs-lookup"><span data-stu-id="dfe64-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="dfe64-189">**Warnungsrichtlinien-ID**</span><span class="sxs-lookup"><span data-stu-id="dfe64-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="dfe64-190">URLs</span><span class="sxs-lookup"><span data-stu-id="dfe64-190">URLs</span></span>

  - <span data-ttu-id="dfe64-191">**URL-Domäne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-191">**URL domain**</span></span>
  - <span data-ttu-id="dfe64-192">**URL-Domäne und Pfad**</span><span class="sxs-lookup"><span data-stu-id="dfe64-192">**URL domain and path**</span></span>
  - <span data-ttu-id="dfe64-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="dfe64-193">**URL**</span></span>
  - <span data-ttu-id="dfe64-194">**URL-Pfad**</span><span class="sxs-lookup"><span data-stu-id="dfe64-194">**URL path**</span></span>
  - <span data-ttu-id="dfe64-195">**Klicken Sie auf Urteil**</span><span class="sxs-lookup"><span data-stu-id="dfe64-195">**Click verdict**</span></span>

<span data-ttu-id="dfe64-196">Für eine erweiterte Filterung, einschließlich der Filterung durch mehrere Eigenschaften, können Sie auf die Schaltfläche **Erweiterter Filter** klicken, um eine Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="dfe64-197">Die gleichen Kampagneneigenschaften sind verfügbar, jedoch mit den folgenden Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="dfe64-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="dfe64-198">Sie können auf **Bedingung hinzufügen** klicken, um mehrere Bedingungen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="dfe64-199">Sie können zwischen Bedingungen den **und-oder-** **Operator auswählen** .</span><span class="sxs-lookup"><span data-stu-id="dfe64-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="dfe64-200">Sie können das Element **Bedingungsgruppe** unten in der Liste Bedingungen auswählen, um komplexe zusammengesetzte Bedingungen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="dfe64-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="dfe64-201">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="dfe64-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="dfe64-202">Nachdem Sie einen einfachen oder erweiterten Filter erstellt haben, können Sie ihn speichern, indem Sie **Abfrage speichern** oder **Abfrage speichern**unter verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfe64-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="dfe64-203">Wenn Sie später zu Kampagnen Ansichten zurückkehren, können Sie einen gespeicherten Filter laden, indem Sie auf **gespeicherte Abfrageeinstellungen**klicken.</span><span class="sxs-lookup"><span data-stu-id="dfe64-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="dfe64-204">Klicken Sie zum Exportieren des Diagramms oder der Kampagnenliste auf **exportieren** , und wählen Sie **Diagrammdaten exportieren** oder **Kampagnenliste**exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="dfe64-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="dfe64-205">Wenn Sie über ein Microsoft Defender ATP-Abonnement verfügen, können Sie auf **WDATP** klicken, um die Kampagneninformationen mit Microsoft Defender ATP zu verbinden oder zu trennen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="dfe64-206">Weitere Informationen finden Sie unter [integrieren Office 365 ATP mit Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="dfe64-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="dfe64-207">Kampagnendetails</span><span class="sxs-lookup"><span data-stu-id="dfe64-207">Campaign details</span></span>

<span data-ttu-id="dfe64-208">Wenn Sie auf den Namen einer Kampagne klicken, werden die kampagnendetails in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="dfe64-209">Kampagneninformationen</span><span class="sxs-lookup"><span data-stu-id="dfe64-209">Campaign information</span></span>

<span data-ttu-id="dfe64-210">Oben in der Ansicht kampagnendetails stehen die folgenden Kampagneninformationen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="dfe64-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="dfe64-211">**ID**: der eindeutige Kampagnen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="dfe64-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="dfe64-212">**Anfang und Ende** **: Startdatum und**Enddatum der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="dfe64-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="dfe64-213">Beachten Sie, dass sich diese Datumsangaben möglicherweise weiter ausdehnen als die Filterdaten, die Sie auf der Übersichtsseite ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="dfe64-214">**Symptom**: Dieser Abschnitt enthält die folgenden Daten für den ausgewählten Datumsbereichsfilter (oder den Sie in der Zeitachse auswählen):</span><span class="sxs-lookup"><span data-stu-id="dfe64-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="dfe64-215">Die Gesamtzahl der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="dfe64-215">The total number of recipients.</span></span>
  - <span data-ttu-id="dfe64-216">Die Anzahl der Nachrichten, die "Posteingang" (also im Posteingang, nicht an den Junk-e-Mail-Ordner) gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="dfe64-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="dfe64-217">Wie viele Benutzer auf die URL-Nutzlast in der Phishing-Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="dfe64-218">Howe viele Benutzer haben die URL besucht.</span><span class="sxs-lookup"><span data-stu-id="dfe64-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="dfe64-219">**Targeted**: der Prozentsatz, der von: (die Anzahl der Kampagnen Empfänger in Ihrer Organisation)/(die Gesamtzahl der Empfänger in der Kampagne für alle Organisationen im Dienst) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="dfe64-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="dfe64-220">Beachten Sie, dass dieser Wert über die gesamte Lebensdauer der Kampagne berechnet wird und nicht die Filterdaten ändert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="dfe64-221">Eine interaktive Zeitachse der Kampagnenaktivität: die Zeitachse zeigt die Aktivität während der gesamten Lebensdauer der Kampagne an.</span><span class="sxs-lookup"><span data-stu-id="dfe64-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="dfe64-222">Standardmäßig enthält der schattierte Bereich den Datumsbereichsfilter, den Sie in der Übersicht ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="dfe64-223">Sie können durch Klicken und ziehen einen bestimmten Startpunkt und Endpunkt auswählen, um <u>die Daten zu ändern, die im **IMPACT** -Bereich angezeigt werden, und auf den Rest der Seite, wie in den nächsten Abschnitten beschrieben</u>.</span><span class="sxs-lookup"><span data-stu-id="dfe64-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="dfe64-224">In der Titelleiste können Sie auf die Schaltfläche Download Campaign Write- **up** klicken, ![ ](../../media/download-campaign-write-up-button.png) um die kampagnendetails in ein Word-Dokument (standardmäßig mit dem Namen "CampaignReport.docx") herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="dfe64-225">Beachten Sie, dass dieses Dokumentdetails über die gesamte Lebensdauer der Kampagne enthält (nicht nur die Filterdaten, die Sie ausgewählt haben).</span><span class="sxs-lookup"><span data-stu-id="dfe64-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Kampagneninformationen](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="dfe64-227">Kampagnenfluss</span><span class="sxs-lookup"><span data-stu-id="dfe64-227">Campaign flow</span></span>

<span data-ttu-id="dfe64-228">In der Mitte der Ansicht kampagnendetails werden wichtige Details zur Kampagne im Abschnitt **Flow** in einem horizontalen Flussdiagramm (als _Sankey_ -Diagramm bezeichnet) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="dfe64-229">Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="dfe64-230">Die Informationen, die im **Fluss** Diagramm angezeigt werden, werden wie im vorherigen Abschnitt beschrieben durch den schattierten Datumsbereich in der Zeitachse gesteuert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="dfe64-232">Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).</span><span class="sxs-lookup"><span data-stu-id="dfe64-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="dfe64-233">Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="dfe64-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="dfe64-234">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="dfe64-234">**Sender IPs**</span></span>

- <span data-ttu-id="dfe64-235">**Absenderdomänen**</span><span class="sxs-lookup"><span data-stu-id="dfe64-235">**Sender domains**</span></span>

- <span data-ttu-id="dfe64-236">**Filter Urteile**: diese Werte beziehen sich auf die verfügbaren Phishing-und Spamfilter Urteile, wie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="dfe64-237">Die verfügbaren Werte werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="dfe64-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="dfe64-238">**Wert**</span><span class="sxs-lookup"><span data-stu-id="dfe64-238">**Value**</span></span>|<span data-ttu-id="dfe64-239">**Spam Filter Urteil**</span><span class="sxs-lookup"><span data-stu-id="dfe64-239">**Spam filter verdict**</span></span>|<span data-ttu-id="dfe64-240">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dfe64-240">**Description**</span></span>|
  |<span data-ttu-id="dfe64-241">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="dfe64-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="dfe64-242">Die Nachricht wurde durch Spamfilterung (beispielsweisedurch eine e-Mail-Fluss Regel, die auch als Transportregel bezeichnet wird) als nicht-Spam und/oder übersprungene Filterung markiert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="dfe64-243">Die Nachricht hat die Spamfilterung aus anderen Gründen übersprungen (beispielsweise scheinen sich der Absender und der Empfänger in derselben Organisation zu befinden).</span><span class="sxs-lookup"><span data-stu-id="dfe64-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="dfe64-244">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="dfe64-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="dfe64-245">Die Nachricht wurde vor der Auswertung durch Spamfilterung (beispielsweisedurch eine Nachrichtenfluss Regel) als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="dfe64-246">**Erkannt**</span><span class="sxs-lookup"><span data-stu-id="dfe64-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="dfe64-247">Die Nachricht wurde von der Spamfilterung als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="dfe64-248">**Nicht erkannt**</span><span class="sxs-lookup"><span data-stu-id="dfe64-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="dfe64-249">Die Nachricht wurde durch Spamfilterung als nicht Spam gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="dfe64-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="dfe64-250">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="dfe64-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="dfe64-251">Die Nachricht hat die Spamfilterung übersprungen, da Sie aus der Quarantäne freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dfe64-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="dfe64-252">**Mandanten zulässig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="dfe64-253">Die Nachricht hat die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen übersprungen (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).</span><span class="sxs-lookup"><span data-stu-id="dfe64-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="dfe64-254">**Mandanten Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="dfe64-255">Die Nachricht wurde durch die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen blockiert (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).</span><span class="sxs-lookup"><span data-stu-id="dfe64-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="dfe64-256">**Benutzer zulassen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="dfe64-257">Die Nachricht hat die Spamfilterung übersprungen, da sich der Absender in Outlook in der Liste sicherer Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="dfe64-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="dfe64-258">**Benutzer Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="dfe64-259">Die Nachricht wurde durch die Spamfilterung blockiert, da sich der Absender in Outlook in der Liste Blockierte Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="dfe64-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="dfe64-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="dfe64-260">**ZAP**</span></span>|<span data-ttu-id="dfe64-261">n/v</span><span class="sxs-lookup"><span data-stu-id="dfe64-261">n/a</span></span>|<span data-ttu-id="dfe64-262">[Zero-Hour Auto Purge (zap)](zero-hour-auto-purge.md) hat in der zugestellten Nachricht entsprechend den Einstellungen Ihrer Antispampolitik (in den Junk-e-Mail-Ordner verschoben oder isoliert) Aktionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="dfe64-263"><sup>\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da die zulässige Nachricht wahrscheinlich vom Dienst blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dfe64-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="dfe64-264"><sup>\*\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da diese Nachrichten isoliert und nicht zugestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="dfe64-265">**Übermittlungsorte**: Sie möchten wahrscheinlich Nachrichten überprüfen, die an Empfänger übermittelt wurden (entweder im Posteingang oder Junk-E-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="dfe64-266">Sie können auch die isolierten Nachrichten aus der Quarantäne entfernen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="dfe64-267">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="dfe64-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="dfe64-268">**Ordner gelöscht**</span><span class="sxs-lookup"><span data-stu-id="dfe64-268">**Deleted folder**</span></span>
  - <span data-ttu-id="dfe64-269">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="dfe64-269">**Dropped**</span></span>
  - <span data-ttu-id="dfe64-270">**Extern**: der Empfänger befindet sich in Ihrer lokalen e-Mail-Organisation in Hybrid Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="dfe64-271">**Fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="dfe64-271">**Failed**</span></span>
  - <span data-ttu-id="dfe64-272">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="dfe64-272">**Forwarded**</span></span>
  - <span data-ttu-id="dfe64-273">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="dfe64-273">**Inbox**</span></span>
  - <span data-ttu-id="dfe64-274">**Junk-E-Mail-Ordner**</span><span class="sxs-lookup"><span data-stu-id="dfe64-274">**Junk folder**</span></span>
  - <span data-ttu-id="dfe64-275">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="dfe64-275">**Quarantine**</span></span>
  - <span data-ttu-id="dfe64-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="dfe64-276">**Unknown**</span></span>

- <span data-ttu-id="dfe64-277">**URL-Klicks**: Diese werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="dfe64-278">In allen Ebenen, die mehr als 10 Elemente enthalten, werden die oberen 10 Elemente angezeigt, während der Rest in **anderen**zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="dfe64-279">URL-Klicks</span><span class="sxs-lookup"><span data-stu-id="dfe64-279">URL clicks</span></span>

<span data-ttu-id="dfe64-280">Wenn eine Phishing-Nachricht an einen Empfänger (in den Posteingang oder den Junk-e-Mail-Ordner) zugestellt wird, besteht immer die Möglichkeit, dass der Benutzer auf die Nutzlast-URL klickt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="dfe64-281">Wenn Sie nicht auf die URL in einer zugestellten Nachricht klicken, ist dies ein kleines Maß an Erfolg, aber Sie müssen herausfinden, warum die Phishing-Nachricht an erster Stelle an Ihr Postfach zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dfe64-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="dfe64-282">Wenn ein Benutzer in der Phishing-Nachricht auf die Nutzlast-URL geklickt hat, werden die Aktionen im Bereich **URL Klicks** des Diagramms in der Ansicht kampagnendetails angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfe64-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="dfe64-283">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="dfe64-283">**Allowed**</span></span>

- <span data-ttu-id="dfe64-284">**BlockPage**: der Empfänger hat auf die Nutzlast-URL geklickt, aber der Zugriff auf die bösartige Website wurde durch die Richtlinien für [ATP-sichere Links](atp-safe-links.md) in Ihrer Organisation blockiert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="dfe64-285">**BlockPageOverride**: der Empfänger hat auf die Nutzlast-URL in der Nachricht geklickt, die ATP-Sicherheits Links haben versucht, diese zu beenden, aber Sie durften den Block außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="dfe64-286">Sie müssen Ihre [Richtlinien zu sicheren Links](set-up-atp-safe-links-policies.md) untersuchen, um zu ermitteln, warum Benutzer das Urteil "sichere Links" außer Kraft setzen und mit der bösartigen Website fortfahren dürfen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="dfe64-287">**PendingDetonationPage**: ATP Safe Attachments ist gerade dabei, die Nutzlast-URL in einer virtuellen Computerumgebung zu öffnen und zu sehen, was geschieht.</span><span class="sxs-lookup"><span data-stu-id="dfe64-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="dfe64-288">**PendingDetonationPageOverride**: der Empfänger durfte den detonations Prozess für die Nutzlast außer Kraft setzen und die URL öffnen, ohne auf die Ergebnisse zu warten.</span><span class="sxs-lookup"><span data-stu-id="dfe64-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="dfe64-289">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="dfe64-289">Tabs</span></span>

<span data-ttu-id="dfe64-290">Auf den Registerkarten in der Ansicht kampagnendetails können Sie die Kampagne weiter untersuchen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="dfe64-291">Die Informationen, die auf den Registerkarten angezeigt werden, werden durch den schattierten Datumsbereich in der Zeitleiste gesteuert, wie im Abschnitt [Kampagneninformationen](#campaign-information) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="dfe64-292">**URL Klicks**: Wenn Benutzer nicht auf die Nutzlast-URL in der Phishing-Nachricht geklickt haben, ist dieser Abschnitt leer.</span><span class="sxs-lookup"><span data-stu-id="dfe64-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="dfe64-293">Wenn ein Benutzer auf die URL klicken konnte, werden die folgenden Werte aufgefüllt:</span><span class="sxs-lookup"><span data-stu-id="dfe64-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="dfe64-294">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="dfe64-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="dfe64-296">**Klicken Sie auf Zeit**</span><span class="sxs-lookup"><span data-stu-id="dfe64-296">**Click time**</span></span>
  - <span data-ttu-id="dfe64-297">**Klicken Sie auf Urteil**</span><span class="sxs-lookup"><span data-stu-id="dfe64-297">**Click verdict**</span></span>

- <span data-ttu-id="dfe64-298">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="dfe64-298">**Sender IPs**</span></span>

  - <span data-ttu-id="dfe64-299">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="dfe64-300">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="dfe64-300">**Total count**</span></span>
  - <span data-ttu-id="dfe64-301">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="dfe64-301">**Inboxed**</span></span>
  - <span data-ttu-id="dfe64-302">**Nicht Posteingang**</span><span class="sxs-lookup"><span data-stu-id="dfe64-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="dfe64-303">**Weitergegebene SPF**: der Absender wurde vom [SPF (Sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="dfe64-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="dfe64-304">Ein Absender, der die SPF-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="dfe64-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="dfe64-305">**Absender**</span><span class="sxs-lookup"><span data-stu-id="dfe64-305">**Senders**</span></span>

  - <span data-ttu-id="dfe64-306">**Absender**: Dies ist die tatsächliche Absenderadresse im SMTP-Mail von-Befehl, die nicht unbedingt die von:-e-Mail-Adresse ist, die Benutzern in Ihren e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dfe64-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="dfe64-307">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="dfe64-307">**Total count**</span></span>
  - <span data-ttu-id="dfe64-308">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="dfe64-308">**Inboxed**</span></span>
  - <span data-ttu-id="dfe64-309">**Nicht Posteingang**</span><span class="sxs-lookup"><span data-stu-id="dfe64-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="dfe64-310">**DKIM-Übergabe**: der Absender wurde durch Domänenschlüssel authentifiziert, die [Mail (DKIM) identifiziert](support-for-validation-of-dkim-signed-messages.md)haben.</span><span class="sxs-lookup"><span data-stu-id="dfe64-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="dfe64-311">Ein Absender, der die DKIM-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="dfe64-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="dfe64-312">**DMARC wurde übergeben**: der Absender wurde durch [domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität authentifiziert (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="dfe64-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="dfe64-313">Ein Absender, der die DMARC-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="dfe64-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="dfe64-314">**Anlagen**</span><span class="sxs-lookup"><span data-stu-id="dfe64-314">**Attachments**</span></span>

  - <span data-ttu-id="dfe64-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="dfe64-315">**Filename**</span></span>
  - <span data-ttu-id="dfe64-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="dfe64-316">**SHA256**</span></span>
  - <span data-ttu-id="dfe64-317">**Schadsoftware-Familie**</span><span class="sxs-lookup"><span data-stu-id="dfe64-317">**Malware family**</span></span>
  - <span data-ttu-id="dfe64-318">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="dfe64-318">**Total count**</span></span>

- <span data-ttu-id="dfe64-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="dfe64-319">**URL**</span></span>

  - <span data-ttu-id="dfe64-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfe64-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="dfe64-321">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="dfe64-321">**Total Count**</span></span>

<span data-ttu-id="dfe64-322"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält.</span><span class="sxs-lookup"><span data-stu-id="dfe64-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="dfe64-323">Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="dfe64-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="dfe64-324">Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="dfe64-324">Buttons</span></span>

<span data-ttu-id="dfe64-325">Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="dfe64-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="dfe64-326">**Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="dfe64-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="dfe64-327">Untersuchen von **Nachrichten im Posteingang**: öffnet eine neue Suchregisterkarte "Threat Explorer" mithilfe der **Kampagnen-ID** und des **Zustellungs Speicherorts: Posteingang** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="dfe64-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
