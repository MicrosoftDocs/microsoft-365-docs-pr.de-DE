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
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209595"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="64cfc-103">Kampagnen Ansichten in ATP</span><span class="sxs-lookup"><span data-stu-id="64cfc-103">Campaign Views in ATP</span></span>

<span data-ttu-id="64cfc-104">Kampagnen Ansichten sind ein Feature in Advanced Threat Protection (ATP) im Security & Compliance Center, das Phishing-Angriffe im Dienst identifiziert und kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="64cfc-105">Kampagnenansichten können Ihnen bei Folgendem helfen:</span><span class="sxs-lookup"><span data-stu-id="64cfc-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="64cfc-106">Phishing-Angriffe effektiv untersuchen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="64cfc-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="64cfc-107">Besseres Verständnis des Umfangs des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="64cfc-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="64cfc-108">Entscheidungsträgern den Nutzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-108">Show value to decision makers.</span></span>

<span data-ttu-id="64cfc-109">Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.</span><span class="sxs-lookup"><span data-stu-id="64cfc-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="64cfc-110">Was ist eine Kampagne?</span><span class="sxs-lookup"><span data-stu-id="64cfc-110">What is a campaign?</span></span>

<span data-ttu-id="64cfc-111">Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="64cfc-112">E-Mail-Angriffe, die Anmeldeinformationen und Unternehmensdaten stehlen, sind eine große und lukrative Branche.</span><span class="sxs-lookup"><span data-stu-id="64cfc-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="64cfc-113">Wenn Technologien sich anstrengen, um Angriffe zu stoppen, ändern Angreifer Ihre Methoden, um den weiteren Erfolg sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="64cfc-114">Microsoft nutzt die großen Mengen an Anti-Phishing-, Antispam-und Antischadsoftware-Daten im gesamten Dienst, um Kampagnen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="64cfc-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="64cfc-115">Wir analysieren und klassifizieren die Angriffsinformationen anhand verschiedener Faktoren.</span><span class="sxs-lookup"><span data-stu-id="64cfc-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="64cfc-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="64cfc-116">For example:</span></span>

- <span data-ttu-id="64cfc-117">**Angriffsquellen**: Quell-IP-Adressen und E-Mail-Domänen des Absenders.</span><span class="sxs-lookup"><span data-stu-id="64cfc-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="64cfc-118">**Eigenschaften der Angriffsnachricht**: Inhalt, Art und Grundstimmung der Angriffsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="64cfc-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="64cfc-119">**Angriffsempfänger**: Empfängerdomänen, Aufgaben des Empfängers (Administratoren, Führungskräfte usw.), Firmentypen (groß, klein, öffentlich, privat usw.) und Branchen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="64cfc-120">**Angriffsnutzlast**: böswillige Links, Anlagen oder andere Nutzlasten in den Angriffs Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="64cfc-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="64cfc-121">Eine Kampagne kann von kurzer Dauer sein oder mehrere Tage, Wochen oder Monate mit aktiven und inaktiven Zeitspannen umfassen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="64cfc-122">Möglicherweise wird eine Kampagne für ihre jeweilige Organisation gestartet, oder Ihre Organisation kann Teil einer größeren Kampagne in mehreren Unternehmen sein.</span><span class="sxs-lookup"><span data-stu-id="64cfc-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="64cfc-123">Kampagnen Ansichten das Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="64cfc-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="64cfc-124">Kampagnen Ansichten stehen im [Security & Compliance Center](https://protection.office.com) unter **Threat Management** \> **Campaigns**zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="64cfc-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Kampagnenübersicht im Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="64cfc-126">Sie können auch die Ansicht Kampagnen Aufrufen von:</span><span class="sxs-lookup"><span data-stu-id="64cfc-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="64cfc-127">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="64cfc-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="64cfc-128">**Threat Management** \> **Explorer** \> **Ansicht anzeigen** \> **Alle e-Mails** \> **Kampagne**</span><span class="sxs-lookup"><span data-stu-id="64cfc-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="64cfc-129">Wenn keine Kampagnendaten angezeigt werden, versuchen Sie, den Zeitraum zu ändern.</span><span class="sxs-lookup"><span data-stu-id="64cfc-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="64cfc-130">Auf der Seite "Übersicht" werden die folgenden Informationen zur Kampagne angezeigt:</span><span class="sxs-lookup"><span data-stu-id="64cfc-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="64cfc-131">**Name**</span><span class="sxs-lookup"><span data-stu-id="64cfc-131">**Name**</span></span>

- <span data-ttu-id="64cfc-132">**Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="64cfc-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="64cfc-133">Beachten Sie, dass alle Nachrichten in der Kampagne nicht unbedingt den gleichen Betreff haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="64cfc-134">**Typ**: derzeit ist dieser Wert immer **Phish**.</span><span class="sxs-lookup"><span data-stu-id="64cfc-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="64cfc-135">**Untertyp**: Wenn verfügbar, die Marke, die von dieser Kampagne ausgespäht wird.</span><span class="sxs-lookup"><span data-stu-id="64cfc-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="64cfc-136">Wenn die Erkennung von der ATP-Technologie gesteuert wird, wird das Präfix **ATP-** dem Untertyp Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="64cfc-137">**Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="64cfc-138">**Inboxed**: die Anzahl der Benutzer, die Nachrichten von dieser Kampagne in Ihrem Posteingang empfangen haben (nicht an Junk zugestellt).</span><span class="sxs-lookup"><span data-stu-id="64cfc-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="64cfc-139">**Geklickt**von: die Anzahl der Benutzer, die auf die URL in der Phishing-Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="64cfc-140">**Klicken Sie auf Rate**: den Prozentsatz,**Clicked**der von "auf  /  **Posteingang**geklickt" berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="64cfc-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="64cfc-141">Dieser Wert ist ein Indikator für die Effektivität der Kampagne und gibt an, ob die Empfänger die Nachricht als Phishing identifizieren konnten, und vermeiden Sie das Klicken auf die Nutzlast-URL.</span><span class="sxs-lookup"><span data-stu-id="64cfc-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="64cfc-142">**Besucht**: Anzahl der Benutzer, die die Nutzlast-Website tatsächlich durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="64cfc-143">Wenn auf Werte **geklickt** wird, aber sichere Links den Zugriff auf die Website blockiert haben, ist dieser Wert gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="64cfc-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="64cfc-144">Wenn Sie auf den Namen einer Kampagne klicken, werden die Kampagnendetails in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="64cfc-145">Kampagnendetails</span><span class="sxs-lookup"><span data-stu-id="64cfc-145">Campaign details</span></span>

<span data-ttu-id="64cfc-146">In der Ansicht "Kampagnendetails" stehen viele Informationen zu der Kampagne bereit:</span><span class="sxs-lookup"><span data-stu-id="64cfc-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="64cfc-147">Kampagneninformationen:</span><span class="sxs-lookup"><span data-stu-id="64cfc-147">Campaign information:</span></span>

  - <span data-ttu-id="64cfc-148">**ID**: der eindeutige Kampagnen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="64cfc-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="64cfc-149">**Begonnen** und **Beendet**: Der ausgewählte Datumsfilter.</span><span class="sxs-lookup"><span data-stu-id="64cfc-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="64cfc-150">**Symptom**: die folgenden Daten für den ausgewählten Datumsbereichsfilter:</span><span class="sxs-lookup"><span data-stu-id="64cfc-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="64cfc-151">Die Gesamtzahl der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="64cfc-151">The total number of recipients.</span></span>

    - <span data-ttu-id="64cfc-152">Die Anzahl der Nachrichten, die "Posteingang" (also im Posteingang, nicht an Junk) gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="64cfc-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="64cfc-153">Wie viele Benutzer auf die URL-Nutzlast in der Phishing-Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="64cfc-154">Howe viele Benutzer haben die URL besucht.</span><span class="sxs-lookup"><span data-stu-id="64cfc-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="64cfc-155">Eine Zeitachse für Kampagnenaktivitäten: Wann die Kampagne begonnen und geendet hat, und die Anzahl der Nachrichten im Zeitverlauf.</span><span class="sxs-lookup"><span data-stu-id="64cfc-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="64cfc-156">Kampagnenfluss</span><span class="sxs-lookup"><span data-stu-id="64cfc-156">Campaign flow</span></span>

<span data-ttu-id="64cfc-157">Wichtige Details zur Kampagne werden in einem horizontalen Flussdiagramm (auch als _Sankey_-Diagramm bezeichnet) im Abschnitt **Fluss** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="64cfc-158">Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="64cfc-160">Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).</span><span class="sxs-lookup"><span data-stu-id="64cfc-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="64cfc-161">Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="64cfc-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="64cfc-162">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="64cfc-162">**Sender IPs**</span></span>

- <span data-ttu-id="64cfc-163">**Absenderdomänen**</span><span class="sxs-lookup"><span data-stu-id="64cfc-163">**Sender domains**</span></span>

- <span data-ttu-id="64cfc-164">**Filter Urteile**: die hier aufgeführten Werte beziehen sich auf die verfügbaren Phishing-und Spamfilter Urteile, wie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="64cfc-165">Die verfügbaren Werte werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="64cfc-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="64cfc-166">Wert</span><span class="sxs-lookup"><span data-stu-id="64cfc-166">Value</span></span>|<span data-ttu-id="64cfc-167">Spam Filter Urteil</span><span class="sxs-lookup"><span data-stu-id="64cfc-167">Spam filter verdict</span></span>|<span data-ttu-id="64cfc-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64cfc-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="64cfc-169">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="64cfc-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="64cfc-170">Die Nachricht wurde durch Spamfilterung (beispielsweisedurch eine e-Mail-Fluss Regel, die auch als Transportregel bezeichnet wird) als nicht-Spam und/oder übersprungene Filterung markiert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="64cfc-171">Die Nachricht hat die Spamfilterung aus anderen Gründen übersprungen (beispielsweise scheinen sich der Absender und der Empfänger in derselben Organisation zu befinden).</span><span class="sxs-lookup"><span data-stu-id="64cfc-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="64cfc-172">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="64cfc-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="64cfc-173">Die Nachricht wurde vor der Auswertung durch Spamfilterung (beispielsweisedurch eine Nachrichtenfluss Regel) als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="64cfc-174">**Erkannt**</span><span class="sxs-lookup"><span data-stu-id="64cfc-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="64cfc-175">Die Nachricht wurde von der Spamfilterung als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="64cfc-176">**Nicht erkannt**</span><span class="sxs-lookup"><span data-stu-id="64cfc-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="64cfc-177">Die Nachricht wurde durch Spamfilterung als nicht Spam gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="64cfc-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="64cfc-178">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="64cfc-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="64cfc-179">Die Nachricht hat die Spamfilterung übersprungen, da Sie aus der Quarantäne freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="64cfc-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="64cfc-180">**Mandanten zulässig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="64cfc-181">Die Nachricht hat die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen übersprungen (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).</span><span class="sxs-lookup"><span data-stu-id="64cfc-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="64cfc-182">**Mandanten Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="64cfc-183">Die Nachricht wurde durch die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen blockiert (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).</span><span class="sxs-lookup"><span data-stu-id="64cfc-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="64cfc-184">**Benutzer zulassen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="64cfc-185">Die Nachricht hat die Spamfilterung übersprungen, da sich der Absender in Outlook in der Liste sicherer Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="64cfc-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="64cfc-186">**Benutzer Block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="64cfc-187">Die Nachricht wurde durch die Spamfilterung blockiert, da sich der Absender in Outlook in der Liste Blockierte Absender eines Benutzers befand.</span><span class="sxs-lookup"><span data-stu-id="64cfc-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="64cfc-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="64cfc-188">**ZAP**</span></span>|<span data-ttu-id="64cfc-189">n/v</span><span class="sxs-lookup"><span data-stu-id="64cfc-189">n/a</span></span>|<span data-ttu-id="64cfc-190">[Zero-Hour Auto Purge (zap)](zero-hour-auto-purge.md) hat in der zugestellten Nachricht entsprechend den Einstellungen Ihrer Antispampolitik (in den Junk-e-Mail-Ordner verschoben oder isoliert) Aktionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="64cfc-191"><sup>\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da die zulässige Nachricht wahrscheinlich vom Dienst blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="64cfc-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="64cfc-192"><sup>\*\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da diese Nachrichten isoliert und nicht zugestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="64cfc-193">**Übermittlungsorte**: Sie möchten wahrscheinlich Nachrichten überprüfen, die an Empfänger übermittelt wurden (entweder im Posteingang oder Junk-E-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="64cfc-194">Sie können auch die isolierten Nachrichten aus der Quarantäne entfernen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="64cfc-195">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="64cfc-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="64cfc-196">**Ordner gelöscht**</span><span class="sxs-lookup"><span data-stu-id="64cfc-196">**Deleted folder**</span></span>

  - <span data-ttu-id="64cfc-197">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="64cfc-197">**Dropped**</span></span>

  - <span data-ttu-id="64cfc-198">**Extern**: der Empfänger befindet sich in Ihrer lokalen e-Mail-Organisation.</span><span class="sxs-lookup"><span data-stu-id="64cfc-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="64cfc-199">**Fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="64cfc-199">**Failed**</span></span>

  - <span data-ttu-id="64cfc-200">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="64cfc-200">**Forwarded**</span></span>

  - <span data-ttu-id="64cfc-201">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="64cfc-201">**Inbox**</span></span>

  - <span data-ttu-id="64cfc-202">**Junk-E-Mail-Ordner**</span><span class="sxs-lookup"><span data-stu-id="64cfc-202">**Junk folder**</span></span>

  - <span data-ttu-id="64cfc-203">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="64cfc-203">**Quarantine**</span></span>

  - <span data-ttu-id="64cfc-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="64cfc-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="64cfc-205">In allen Ebenen, die mehr als 10 Elemente enthalten, werden die oberen 10 Elemente angezeigt, während der Rest in **anderen**zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="64cfc-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="64cfc-206">URL-Klicks</span><span class="sxs-lookup"><span data-stu-id="64cfc-206">URL clicks</span></span>

<span data-ttu-id="64cfc-207">Wenn eine Phishing-Nachricht an einen Empfänger (in den Posteingang oder den Junk-e-Mail-Ordner) zugestellt wird, besteht immer die Möglichkeit, dass der Benutzer auf die Nutzlast-URL klickt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="64cfc-208">Wenn Sie nicht auf die URL in einer zugestellten Nachricht klicken, ist dies ein kleines Maß an Erfolg, aber Sie müssen herausfinden, warum die Phishing-Nachricht an erster Stelle an Ihr Postfach zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="64cfc-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="64cfc-209">Wenn ein Benutzer in der Phishing-Nachricht auf die Nutzlast-URL geklickt hat, werden die Aktionen im Bereich **URL Klicks** des Diagramms in der Ansicht kampagnendetails angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64cfc-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="64cfc-210">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="64cfc-210">**Allowed**</span></span>

- <span data-ttu-id="64cfc-211">**BlockPage**: der Empfänger hat auf die Nutzlast-URL geklickt, aber der Zugriff auf die bösartige Website wurde durch die Richtlinien für [ATP-sichere Links](atp-safe-links.md) in Ihrer Organisation blockiert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="64cfc-212">**BlockPageOverride**: der Empfänger hat auf die Nutzlast-URL in der Nachricht geklickt, die ATP-Sicherheits Links haben versucht, diese zu beenden, aber Sie durften den Block außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="64cfc-213">Sie müssen Ihre [Richtlinien zu sicheren Links](set-up-atp-safe-links-policies.md) untersuchen, um zu ermitteln, warum Benutzer das Urteil "sichere Links" außer Kraft setzen und mit der bösartigen Website fortfahren dürfen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="64cfc-214">**PendingDetonationPage**: ATP Safe Attachments ist gerade dabei, die Nutzlast-URL in einer virtuellen Computerumgebung zu öffnen und zu sehen, was geschieht.</span><span class="sxs-lookup"><span data-stu-id="64cfc-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="64cfc-215">**PendingDetonationPageOverride**: der Empfänger durfte den detonations Prozess für die Nutzlast außer Kraft setzen und die URL öffnen, ohne auf die Ergebnisse zu warten.</span><span class="sxs-lookup"><span data-stu-id="64cfc-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="64cfc-216">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="64cfc-216">Tabs</span></span>

<span data-ttu-id="64cfc-217">In der Ansicht „Kampagnendetails“ stehen mehrere Registerkarten zur Verfügung, mit denen Sie die Kampagne weiter untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="64cfc-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="64cfc-218">**URL Klicks**: Wenn Benutzer nicht auf die Nutzlast-URL in der Phishing-Nachricht geklickt haben, ist dieser Abschnitt leer.</span><span class="sxs-lookup"><span data-stu-id="64cfc-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="64cfc-219">Wenn ein Benutzer auf die URL klicken konnte, werden die folgenden Werte aufgefüllt:</span><span class="sxs-lookup"><span data-stu-id="64cfc-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="64cfc-220">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="64cfc-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="64cfc-222">**Zeit**</span><span class="sxs-lookup"><span data-stu-id="64cfc-222">**Click Time**</span></span>

  - <span data-ttu-id="64cfc-223">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="64cfc-223">**Click Action**</span></span>

- <span data-ttu-id="64cfc-224">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="64cfc-224">**Sender IPs**</span></span>

  - <span data-ttu-id="64cfc-225">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="64cfc-226">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="64cfc-226">**Total Count**</span></span>

  - <span data-ttu-id="64cfc-227">**Anzahl "Posteingang"**</span><span class="sxs-lookup"><span data-stu-id="64cfc-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="64cfc-228">**Anzahl "Gesperrt"**</span><span class="sxs-lookup"><span data-stu-id="64cfc-228">**Blocked Count**</span></span>

  - <span data-ttu-id="64cfc-229">**Weitergegebene SPF**: der Absender wurde vom [SPF (Sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="64cfc-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="64cfc-230">Ein Absender, der die SPF-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="64cfc-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="64cfc-231">**Absender**</span><span class="sxs-lookup"><span data-stu-id="64cfc-231">**Senders**</span></span>

  - <span data-ttu-id="64cfc-232">**Absender**: Dies ist die tatsächliche Absenderadresse im SMTP-Mail von-Befehl, die nicht unbedingt die von:-e-Mail-Adresse ist, die Benutzern in Ihren e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64cfc-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="64cfc-233">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="64cfc-233">**Total Count**</span></span>

  - <span data-ttu-id="64cfc-234">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="64cfc-234">**Inboxed**</span></span>

  - <span data-ttu-id="64cfc-235">**Nicht Posteingang**</span><span class="sxs-lookup"><span data-stu-id="64cfc-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="64cfc-236">**DKIM-Übergabe**: der Absender wurde durch Domänenschlüssel authentifiziert, die [Mail (DKIM) identifiziert](support-for-validation-of-dkim-signed-messages.md)haben.</span><span class="sxs-lookup"><span data-stu-id="64cfc-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="64cfc-237">Ein Absender, der die DKIM-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="64cfc-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="64cfc-238">**DMARC wurde übergeben**: der Absender wurde durch [domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität authentifiziert (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="64cfc-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="64cfc-239">Ein Absender, der die DMARC-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.</span><span class="sxs-lookup"><span data-stu-id="64cfc-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="64cfc-240">**Nutzlasten**</span><span class="sxs-lookup"><span data-stu-id="64cfc-240">**Payloads**</span></span>

  - <span data-ttu-id="64cfc-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="64cfc-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="64cfc-242">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="64cfc-242">**Total Count**</span></span>

<span data-ttu-id="64cfc-243"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält.</span><span class="sxs-lookup"><span data-stu-id="64cfc-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="64cfc-244">Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="64cfc-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="64cfc-245">Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="64cfc-245">Buttons</span></span>

<span data-ttu-id="64cfc-246">Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="64cfc-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="64cfc-247">**Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="64cfc-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="64cfc-248">Untersuchen von **Nachrichten im Posteingang**: öffnet eine neue Suchregisterkarte "Threat Explorer" mithilfe der **Kampagnen-ID** und des **Zustellungs Speicherorts: Posteingang** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="64cfc-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
