---
title: Exemplarische Vorgehensweise – Spoof Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie die Spoof Intelligence-Einblicke funktionieren. Sie können schnell ermitteln, welche Absender legitimerweise e-Mails in ihre Organisationen aus Domänen senden, die keine e-Mail-Authentifizierungsprüfungen (SPF, DKIM oder DMARC) durchführen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920478"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1a6c6-104">Exemplarische Vorgehensweise – Spoof Intelligence Insight in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1a6c6-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1a6c6-105">In Microsoft 365-Organisationen mit Defender for Office 365 können Sie die Spoof Intelligence-Einblicke verwenden, um schnell zu ermitteln, welche Absender legitimerweise nicht authentifizierte e-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM-oder DMARC-Überprüfungen durchführen).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="1a6c6-106">Wenn Sie zulassen, dass bekannte Absender gefälschte Nachrichten von bekannten Speicherorten senden, können Sie falsch positive Ergebnisse reduzieren (gute e-Mail-Nachrichten sind als ungültig markiert).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="1a6c6-107">Durch Überwachen der zulässigen gefälschten Absender stellen Sie eine zusätzliche Sicherheitsebene bereit, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation eingehen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="1a6c6-108">Weitere Informationen zu Berichten und Einblicken finden Sie unter [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="1a6c6-109">Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="1a6c6-110">Informationen zum Navigieren in Berichten und Einblicken finden Sie unter Exemplarische Vorgehensweisen im Abschnitt " [Verwandte Themen](#related-topics) ".</span><span class="sxs-lookup"><span data-stu-id="1a6c6-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a6c6-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1a6c6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a6c6-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1a6c6-113">Um direkt zur Seite **Security Dashboard** zu wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="1a6c6-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="1a6c6-114">Sie können die Einblicke in Spoof Intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="1a6c6-115">Unabhängig davon, für welches Dashboard Sie sich interessieren, bietet die Insight dieselben Details und ermöglicht Ihnen, schnell dieselben Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="1a6c6-116">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="1a6c6-117">Um die Spoof Intelligence-Einblicke verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="1a6c6-118">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="1a6c6-119">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="1a6c6-120">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="1a6c6-121">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="1a6c6-122">Sie aktivieren und deaktivieren Spoof Intelligence in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1a6c6-123">Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="1a6c6-124">Informationen zum Verwenden von Spoof Intelligence zum Überwachen und Verwalten von Absendern, die nicht authentifizierte Nachrichten senden, finden Sie unter [configure Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="1a6c6-125">Öffnen Sie die Spoof Intelligence-Einblicke im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="1a6c6-126">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="1a6c6-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="1a6c6-127">Suchen Sie in der Zeile **Insights** nach einem der folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="1a6c6-128">**Spoof Intelligence ist aktiviert** : die Einblicke werden als **gefälschte Domänen bezeichnet, bei denen die Authentifizierung der letzten 30 Tage nicht erfolgreich** war.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="1a6c6-129">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-129">This is the default.</span></span>
   - <span data-ttu-id="1a6c6-130">**Spoof Intelligence ist deaktiviert** : die Einblicke in benannten **aktivieren Spoof Protection** , und klicken Sie auf Sie können Sie Spoof Intelligence aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="1a6c6-131">Die Einblicke in das Dashboard zeigt Ihnen Informationen wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-131">The insight on the dashboard shows you information like this:</span></span>

   ![Screenshot von Spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="1a6c6-133">Diese Einblicke umfasst zwei Modi:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-133">This insight has two modes:</span></span>

   - <span data-ttu-id="1a6c6-134">**Insight-Modus** : Wenn Spoof Intelligence aktiviert ist, zeigt Ihnen die Einblicke, wie viele Nachrichten in den letzten 30 Tagen durch unsere Spoof Intelligence-Funktionen beeinflusst wurden.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="1a6c6-135">**Was** ist, wenn-Modus: Wenn Spoof Intelligence deaktiviert ist, dann zeigt Ihnen die Einsicht, wie viele Nachrichten in den letzten 30 Tagen von unseren Spoof Intelligence-Funktionen betroffen *wären* .</span><span class="sxs-lookup"><span data-stu-id="1a6c6-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="1a6c6-136">In beiden Fällen werden die in der Insight angezeigten gefälschten Domänen in zwei Kategorien unterteilt: **verdächtige Domänen Paare** und **nicht verdächtige Domänen Paare**.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="1a6c6-137">Diese Kategorien werden weiter in drei verschiedene Buckets unterteilt, die Sie überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="1a6c6-138">Ein **Domänenpaar** ist eine Kombination aus der von-Adresse und der sendenden Infrastruktur:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="1a6c6-139">Die Absenderadresse ist die e-Mail-Adresse des Absenders, die im Feld von in e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="1a6c6-140">Diese Adresse wird auch als Adresse bezeichnet `5322.From` .</span><span class="sxs-lookup"><span data-stu-id="1a6c6-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="1a6c6-141">Die sendende Infrastruktur oder der Absender ist die Organisationsdomäne des Reverse-DNS-Lookups (PTR-Eintrags) der sendenden IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="1a6c6-142">Wenn die sendende IP-Adresse keinen PTR-Eintrag hat, wird der Absender von der sendenden IP mit der Subnetzmaske 255.255.255.0 in der CIDR-Notation (/24) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="1a6c6-143">Wenn die IP-Adresse beispielsweise 192.168.100.100 lautet, lautet die vollständige IP-Adresse des Absenders 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="1a6c6-144">Zu den **verdächtigen Domänen Paaren** gehören:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="1a6c6-145">**Spoofing mit hoher Vertrauens** Würdigkeit: basierend auf den Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen sind wir sehr zuversichtlich, dass die Domänen Spoofing sind und Nachrichten aus diesen Domänen eher bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="1a6c6-146">**Gemäßigte Vertrauens Parodie** : basierend auf Verlaufs Sende Mustern und dem Reputationswert der Domänen sind wir mit mittlerer Zuversicht überzeugt, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten legitim sind.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="1a6c6-147">Falsch positive Ergebnisse sind in dieser Kategorie eher als hochgradig vertrauenswürdige Spoofing.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="1a6c6-148">**Nicht verdächtige Domänen Paare** (einschließlich **geretteter Spoofing** ): die Domänen-fehlgeschlagene explizite e-Mail-Authentifizierung überprüft [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="1a6c6-149">Die Domäne bestanden jedoch unsere impliziten e-Mail-Authentifizierungsprüfungen ([kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="1a6c6-150">Dies hat zur Folge, dass keine Anti-Spoofing-Aktion für die Nachricht durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="1a6c6-151">Anzeigen detaillierter Informationen zu verdächtigen Domänen Paaren aus dem Spoof Intelligence-Insight</span><span class="sxs-lookup"><span data-stu-id="1a6c6-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="1a6c6-152">Klicken Sie auf der Spoof Intelligence-Einblicke auf eines der Domänen Paare (hoch, moderat oder gerettet).</span><span class="sxs-lookup"><span data-stu-id="1a6c6-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="1a6c6-153">Die Seite **Spoof Intelligence Insight** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="1a6c6-154">Auf der Seite wird eine Liste mit Absendern angezeigt, die nicht authentifizierte e-Mails an Ihre Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="1a6c6-155">Anhand dieser Informationen können Sie bestimmen, ob gefälschte Nachrichten autorisiert sind oder ob Sie weitere Aktionen ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="1a6c6-156">Sie können die Informationen nach Nachrichtenanzahl, dem Datum, an dem die Spoof zuletzt erkannt wurde, und vieles mehr sortieren.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="1a6c6-157">Wählen Sie ein Element in der Tabelle aus, um einen Detailbereich mit umfangreichen Informationen zum Domänenpaar zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="1a6c6-158">Die Informationen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-158">The information includes:</span></span>
   - <span data-ttu-id="1a6c6-159">Warum wir dies erwischt haben.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-159">Why we caught this.</span></span>
   - <span data-ttu-id="1a6c6-160">Was Sie tun müssen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-160">What you need to do.</span></span>
   - <span data-ttu-id="1a6c6-161">Eine Domänen Zusammenfassung.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-161">A domain summary.</span></span>
   - <span data-ttu-id="1a6c6-162">Whois-Daten über den Absender.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="1a6c6-163">Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="1a6c6-164">Von hier aus können Sie auch das Domänenpaar aus der Liste sicherer Absender von **AllowedToSpoof** hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="1a6c6-166">Hinzufügen oder Entfernen einer Domäne aus der AllowedToSpoof-Liste</span><span class="sxs-lookup"><span data-stu-id="1a6c6-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="1a6c6-167">Sie fügen oder entfernen eine Domäne aus der Liste AllowedToSpoof (Safe Sender) im Detailbereich des Spoof Intelligence Insight für das Domänenpaar.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="1a6c6-168">Legen Sie die Umschaltfläche einfach entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="1a6c6-169">Wenn ein Domänenpaar nur zugelassen wird, ist die Kombination aus der gefälschten Domäne *und* der sendenden Infrastruktur möglich.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="1a6c6-170">Es werden keine e-Mails von der gefälschten Domäne aus einer beliebigen Quelle zugelassen, und es werden keine e-Mails von der sendenden Infrastruktur für eine beliebige Domäne zugelassen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="1a6c6-171">Beispielsweise können Sie dem folgenden Domänenpaar Spoofing-Nachrichten an Ihre Organisation senden:</span><span class="sxs-lookup"><span data-stu-id="1a6c6-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="1a6c6-172">*Spoofing-Domäne* : gmail.com "</span><span class="sxs-lookup"><span data-stu-id="1a6c6-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="1a6c6-173">*Sendende Infrastruktur* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="1a6c6-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="1a6c6-174">Nur e-Mails von diesem Domänenpaar dürfen Spoofing durchgehen.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="1a6c6-175">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="1a6c6-176">Nachrichten in anderen Domänen von TMS.MX.com werden durch Spoof Intelligence überprüft.</span><span class="sxs-lookup"><span data-stu-id="1a6c6-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a6c6-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1a6c6-177">Related topics</span></span>

[<span data-ttu-id="1a6c6-178">Schutz gegen Spoofing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a6c6-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
