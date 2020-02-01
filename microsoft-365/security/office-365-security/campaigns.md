---
title: Kampagnenansichten in Office 365 ATP
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
ms.openlocfilehash: 65ae346fc4ffdcc502c7f479d7d92753cdb5b5bc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599762"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="1257a-103">Kampagnenansichten in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1257a-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="1257a-104">Die in diesem Thema beschriebenen Features sind derzeit als Vorschauversionen verfügbar und können jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1257a-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="1257a-105">Kampagnenansichten ist ein Feature von Advanced Threat Protection (ATP) im Office 365 Security & Compliance Center, das Phishing-Angriffe im Dienst identifiziert und kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="1257a-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="1257a-106">Kampagnenansichten können Ihnen bei Folgendem helfen:</span><span class="sxs-lookup"><span data-stu-id="1257a-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="1257a-107">Phishing-Angriffe effektiv untersuchen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="1257a-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="1257a-108">Besseres Verständnis des Umfangs des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="1257a-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="1257a-109">Entscheidungsträgern den Nutzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1257a-109">Show value to decision makers.</span></span>

<span data-ttu-id="1257a-110">Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.</span><span class="sxs-lookup"><span data-stu-id="1257a-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="1257a-111">Was ist eine Kampagne?</span><span class="sxs-lookup"><span data-stu-id="1257a-111">What is a campaign?</span></span>

<span data-ttu-id="1257a-112">Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen.</span><span class="sxs-lookup"><span data-stu-id="1257a-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="1257a-113">Heutzutage sind E-Mail-Angriffe, mit denen Anmeldeinformationen und Unternehmensdaten gestohlen werden, ein großes und lukratives Geschäft.</span><span class="sxs-lookup"><span data-stu-id="1257a-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="1257a-114">Zwar werden die Technologien, um Angreifer zu stoppen, immer weiter verbessert, aber die Angreifer sind raffiniert genug, ihre Methoden immer wieder zu ändern und so weiterhin erfolgreich zu sein. </span><span class="sxs-lookup"><span data-stu-id="1257a-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="1257a-115">Microsoft nutzt die riesigen Mengen an Anti-Phishing-, Anti-Spam- und Antischadsoftware-Daten und -Erfahrungen weltweit im gesamten Office 365-Dienst, um Kampagnen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1257a-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="1257a-116">Die Angriffsinformationen werden analysiert und nach mehreren Faktoren klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="1257a-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="1257a-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1257a-117">For example:</span></span>

- <span data-ttu-id="1257a-118">**Angriffsquellen**: Quell-IP-Adressen und E-Mail-Domänen des Absenders.</span><span class="sxs-lookup"><span data-stu-id="1257a-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="1257a-119">**Eigenschaften der Angriffsnachricht**: Inhalt, Art und Grundstimmung der Angriffsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="1257a-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="1257a-120">**Angriffsempfänger**: Empfängerdomänen, Aufgaben des Empfängers (Administratoren, Führungskräfte usw.), Firmentypen (groß, klein, öffentlich, privat usw.) und Branchen.</span><span class="sxs-lookup"><span data-stu-id="1257a-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="1257a-121">**Angriffsnutzlast**: Bösartige Links, Anlagen oder andere Nutzlasten.</span><span class="sxs-lookup"><span data-stu-id="1257a-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="1257a-122">Kampagnenansichten im Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1257a-122">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="1257a-123">Kampagnenansichten stehen im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) an den folgenden Speicherorten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1257a-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="1257a-124">**Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Phishing** \> **Top-Kampagne (Vorschau)**</span><span class="sxs-lookup"><span data-stu-id="1257a-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="1257a-125">**Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Alle E-Mails** \> **Top-Kampagne (Vorschau)**</span><span class="sxs-lookup"><span data-stu-id="1257a-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![Kampagnenübersicht im Security & Compliance Center](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="1257a-127">Derzeit kann nur nach dem Zeitraum gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="1257a-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="1257a-128">Wenn keine Kampagnendaten angezeigt werden, versuchen Sie, den Zeitraum zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1257a-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="1257a-129">Auf der Seite "Übersicht" werden die folgenden Informationen zur Kampagne angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1257a-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="1257a-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="1257a-130">**Name**</span></span>

- <span data-ttu-id="1257a-131">**Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="1257a-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="1257a-132">Beachten Sie, dass nicht unbedingt _alle_ Nachrichten der Kampagne die gleiche Betreffzeile besitzen.</span><span class="sxs-lookup"><span data-stu-id="1257a-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="1257a-133">**Typ**: Dieser Wert ist derzeit immer **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="1257a-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="1257a-134">**Untertyp**: Wenn verfügbar, die Marke, die von dieser Kampagne ausgespäht wird.</span><span class="sxs-lookup"><span data-stu-id="1257a-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="1257a-135">Wenn die Erkennung durch die ATP-Technologie gesteuert wird, wird das Präfix **ATP-** zum Wert "Untertyp" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1257a-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="1257a-136">**Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.</span><span class="sxs-lookup"><span data-stu-id="1257a-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="1257a-137">**Zugestellt**: Die Anzahl der Benutzer, die Nachrichten dieser Kampagne in Ihrem Posteingang empfangen haben.</span><span class="sxs-lookup"><span data-stu-id="1257a-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="1257a-138">**ID**: Ein eindeutiger Bezeichner für die Kampagne.</span><span class="sxs-lookup"><span data-stu-id="1257a-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="1257a-139">Wenn Sie auf den Namen einer Kampagne klicken, werden die Kampagnendetails in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1257a-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="1257a-140">Kampagnendetails</span><span class="sxs-lookup"><span data-stu-id="1257a-140">Campaign details</span></span>

<span data-ttu-id="1257a-141">In der Ansicht "Kampagnendetails" stehen viele Informationen zu der Kampagne bereit:</span><span class="sxs-lookup"><span data-stu-id="1257a-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="1257a-142">Kampagneninformationen:</span><span class="sxs-lookup"><span data-stu-id="1257a-142">Campaign information:</span></span>

  - <span data-ttu-id="1257a-143">**ID**: Der eindeutige Bezeichner der Kampagne von der Übersichtsseite.</span><span class="sxs-lookup"><span data-stu-id="1257a-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="1257a-144">**Begonnen** und **Beendet**: Der ausgewählte Datumsfilter.</span><span class="sxs-lookup"><span data-stu-id="1257a-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="1257a-145">**Auswirkung**: Die Anzahl der Nachrichten, die in dem von Ihnen ausgewählten Datumsabschnitt gesendet wurden, wie viele Nachrichten in den Posteingang übertragen wurden und wie viele Benutzer auf die URL-Nutzlast in der Phishing-Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="1257a-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="1257a-146">Eine Zeitachse für Kampagnenaktivitäten: Wann die Kampagne begonnen und geendet hat, und die Anzahl der Nachrichten im Zeitverlauf.</span><span class="sxs-lookup"><span data-stu-id="1257a-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="1257a-147">Kampagnenfluss</span><span class="sxs-lookup"><span data-stu-id="1257a-147">Campaign flow</span></span>

<span data-ttu-id="1257a-148">Wichtige Details zur Kampagne werden in einem horizontalen Flussdiagramm (auch als _Sankey_-Diagramm bezeichnet) im Abschnitt **Fluss** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1257a-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="1257a-149">Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="1257a-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="1257a-151">Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).</span><span class="sxs-lookup"><span data-stu-id="1257a-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="1257a-152">Das Diagramm enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="1257a-152">The diagram contains the following information:</span></span>

- <span data-ttu-id="1257a-153">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="1257a-153">**Sender IPs**</span></span>

- <span data-ttu-id="1257a-154">**Absenderdomänen**</span><span class="sxs-lookup"><span data-stu-id="1257a-154">**Sender domains**</span></span>

- <span data-ttu-id="1257a-155">**Filterbewertungen**: Die hier aufgeführten Werte beziehen sich auf die verfügbaren Anti-Phishing- und Anti-Spam-Filterbewertungen, die in [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="1257a-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="1257a-156">Besonders interessant sind hier die Werte **Mandantenzulassung**, was bedeutet, dass eine konfigurierte Einstellung in der Organisation eine Nachricht durchgelassen hat, die andernfalls vom Dienst blockiert worden wäre (z. B. eine Domäne in der Liste der zulässigen Absender).</span><span class="sxs-lookup"><span data-stu-id="1257a-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="1257a-157">**Mandantensperre**: Dieser Wert gibt an, dass eine Einstellung in Ihrer Organisation (z. B. ein Domäneneintrag in der [Liste der blockierten Absender](create-block-sender-lists-in-office-365.md)) die Nachricht erkannt und ermittelt hat, wo sie zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1257a-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="1257a-158">Bei Nachrichten, die nicht isoliert wurden, überprüfen Sie die Einstellungen der blockierten Absender, um zu ermitteln, warum die Nachricht zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1257a-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="1257a-159">**Erkannt**</span><span class="sxs-lookup"><span data-stu-id="1257a-159">**Detected**</span></span>

  - <span data-ttu-id="1257a-160">**Mandantenzulassung**</span><span class="sxs-lookup"><span data-stu-id="1257a-160">**Tenant Allow**</span></span>

- <span data-ttu-id="1257a-161">**Übermittlungsorte**: Sie möchten wahrscheinlich Nachrichten überprüfen, die an Empfänger übermittelt wurden (entweder im Posteingang oder Junk-E-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="1257a-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="1257a-162">Sie können zudem die isolierten Nachrichten aus den [Quarantäne-E-Mail-Nachrichten in Office 365](quarantine-email-messages.md) entfernen.</span><span class="sxs-lookup"><span data-stu-id="1257a-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="1257a-163">**Junk-E-Mail-Ordner**</span><span class="sxs-lookup"><span data-stu-id="1257a-163">**Junk folder**</span></span>

  - <span data-ttu-id="1257a-164">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="1257a-164">**Quarantine**</span></span>

  - <span data-ttu-id="1257a-165">**Posteingang**</span><span class="sxs-lookup"><span data-stu-id="1257a-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="1257a-166">URL-Klicks</span><span class="sxs-lookup"><span data-stu-id="1257a-166">URL clicks</span></span>

<span data-ttu-id="1257a-167">Es ist immer möglich, dass Nachrichten, die an den Posteingang oder den Junk-E-Mail-Ordner des Empfängers gesendet wurden, vom Benutzer bearbeitet werden (d. h. der Benutzer klickt auf den bösartigen URL in der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="1257a-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="1257a-168">Wenn dies nicht der Fall ist, ist dies ein kleiner Erfolg, aber Sie müssen dennoch unbedingt ermitteln, warum die schädliche Nachricht an das Postfach übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1257a-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="1257a-169">Wenn ein Benutzer auf die bösartige URL geklickt hat, werden die Aktionen im Bereich **URL-Klicks** des Diagramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1257a-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![Kampagnendetails, die Benutzer-URL-Klicks enthalten](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="1257a-171">**Sichere Links-Sperre**: Dieser Wert gibt an, dass der Empfänger auf die Nutzlast-URL in der Nachricht geklickt hat, sie jedoch durch die Richtlinien für [ATP-sichere Links](atp-safe-links.md) in Ihrer Organisation blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1257a-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="1257a-172">**Sichere Links-Sperre außer Kraft gesetzt**: Dieser Wert gibt an, dass der Empfänger auf die Nutzlast-URL in der Nachricht geklickt hat und ATP-sichere Links versucht haben, diese zu beenden, die Sperre jedoch überschrieben werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1257a-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="1257a-173">Sie müssen ihre [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) überprüfen, um herauszufinden, warum Benutzer das Urteil "Sichere Links" außer Kraft setzen und auf bösartige URLs klicken konnten.</span><span class="sxs-lookup"><span data-stu-id="1257a-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="1257a-174">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="1257a-174">Tabs</span></span>

<span data-ttu-id="1257a-175">In der Ansicht „Kampagnendetails“ stehen mehrere Registerkarten zur Verfügung, mit denen Sie die Kampagne weiter untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="1257a-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="1257a-176">**URL-Klicks**: Wenn die Nutzlast-URL in der Phishing-Nachricht nicht angeklickt wurde, ist dieser Abschnitt leer.</span><span class="sxs-lookup"><span data-stu-id="1257a-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="1257a-177">Wenn ein Benutzer auf die URL klicken konnte, wählen Sie:</span><span class="sxs-lookup"><span data-stu-id="1257a-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="1257a-178">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1257a-178">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="1257a-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1257a-179">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="1257a-180">**Zeit**</span><span class="sxs-lookup"><span data-stu-id="1257a-180">**Click Time**</span></span>

  - <span data-ttu-id="1257a-181">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="1257a-181">**Click Action**</span></span>

- <span data-ttu-id="1257a-182">**Sender-IPs**</span><span class="sxs-lookup"><span data-stu-id="1257a-182">**Sender IPs**</span></span>

  - <span data-ttu-id="1257a-183">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1257a-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="1257a-184">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="1257a-184">**Total Count**</span></span>

  - <span data-ttu-id="1257a-185">**Anzahl "Posteingang"**</span><span class="sxs-lookup"><span data-stu-id="1257a-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="1257a-186">**Anzahl "Gesperrt"**</span><span class="sxs-lookup"><span data-stu-id="1257a-186">**Blocked Count**</span></span>

  - <span data-ttu-id="1257a-187">**SPF übergeben**</span><span class="sxs-lookup"><span data-stu-id="1257a-187">**SPF Passed**</span></span>

- <span data-ttu-id="1257a-188">**Absender**</span><span class="sxs-lookup"><span data-stu-id="1257a-188">**Senders**</span></span>

  - <span data-ttu-id="1257a-189">**Absender**</span><span class="sxs-lookup"><span data-stu-id="1257a-189">**Sender**</span></span>

  - <span data-ttu-id="1257a-190">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="1257a-190">**Total Count**</span></span>

  - <span data-ttu-id="1257a-191">**Anzahl "Posteingang"**</span><span class="sxs-lookup"><span data-stu-id="1257a-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="1257a-192">**Anzahl "Gesperrt"**</span><span class="sxs-lookup"><span data-stu-id="1257a-192">**Blocked Count**</span></span>

  - <span data-ttu-id="1257a-193">**DKIM übergeben**</span><span class="sxs-lookup"><span data-stu-id="1257a-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="1257a-194">**DMARC übergeben**</span><span class="sxs-lookup"><span data-stu-id="1257a-194">**DMARC Passed**</span></span>

- <span data-ttu-id="1257a-195">**Nutzlasten**</span><span class="sxs-lookup"><span data-stu-id="1257a-195">**Payloads**</span></span>

  - <span data-ttu-id="1257a-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1257a-196">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="1257a-197">**Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="1257a-197">**Total Count**</span></span>

<span data-ttu-id="1257a-198"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält.</span><span class="sxs-lookup"><span data-stu-id="1257a-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="1257a-199">Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="1257a-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="1257a-200">Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="1257a-200">Buttons</span></span>

<span data-ttu-id="1257a-201">Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1257a-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="1257a-202">**Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.</span><span class="sxs-lookup"><span data-stu-id="1257a-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="1257a-203">**Nachrichten im Posteingang durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit den Suchfiltern **Kampagnen-ID** und **Übermittlungsort: Posteingang**.</span><span class="sxs-lookup"><span data-stu-id="1257a-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
