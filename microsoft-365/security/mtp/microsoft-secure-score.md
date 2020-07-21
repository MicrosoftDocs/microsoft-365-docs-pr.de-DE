---
title: Microsoft Secure Score
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitsposition verbessern und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200038"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="58c24-104">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="58c24-104">Microsoft Secure Score</span></span>

<span data-ttu-id="58c24-105">Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="58c24-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="58c24-106">Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="58c24-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="58c24-107">Wenn Sie die Secure Score-Empfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen.</span><span class="sxs-lookup"><span data-stu-id="58c24-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="58c24-108">Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und daran arbeiten.</span><span class="sxs-lookup"><span data-stu-id="58c24-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="58c24-109">Sicherheitsbewertung hilft Organisationen auf diese Arten:</span><span class="sxs-lookup"><span data-stu-id="58c24-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="58c24-110">Berichtet über den aktuellen Sicherheitsstatus der Organisation.</span><span class="sxs-lookup"><span data-stu-id="58c24-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="58c24-111">Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="58c24-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="58c24-112">Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="58c24-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="58c24-113">Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="58c24-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="58c24-114">Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="58c24-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="58c24-116">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="58c24-116">How it works</span></span>

<span data-ttu-id="58c24-117">Sie erhalten Punkte für die Konfiguration empfohlener Sicherheitsfunktionen, die Ausführung sicherheitsrelevanter Aufgaben oder die Behandlung von Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software oder einer alternativen Korrektur.</span><span class="sxs-lookup"><span data-stu-id="58c24-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="58c24-118">Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind, und einige geben schon Punkte, auch wenn sie nur für einige Geräte oder Benutzer abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="58c24-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="58c24-119">Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="58c24-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="58c24-120">Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Ihnen Empfehlungen für diese Produkte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58c24-120">If you have a license for one of the supported Microsoft products, then you will see recommendations for those products.</span></span> <span data-ttu-id="58c24-121">Wir zeigen Ihnen den vollständigen Überblick über mögliche Verbesserungen für ein Produkt, unabhängig von Lizenzedition, Abonnement oder Plan, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können.</span><span class="sxs-lookup"><span data-stu-id="58c24-121">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="58c24-122">Ihre absolute Sicherheitsposition wird durch Secure Score dargestellt, was unabhängig von den Lizenzen, die Ihre Organisation für ein bestimmtes Produkt besitzt, gleich bleibt.</span><span class="sxs-lookup"><span data-stu-id="58c24-122">Your absolute security posture is represented by Secure Score, which stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="58c24-123">Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="58c24-123">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="58c24-124">Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="58c24-124">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="58c24-125">Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58c24-125">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="58c24-126">Schlüsselszenarien</span><span class="sxs-lookup"><span data-stu-id="58c24-126">Key scenarios</span></span>

- [<span data-ttu-id="58c24-127">Überprüfen der aktuellen Bewertung</span><span class="sxs-lookup"><span data-stu-id="58c24-127">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="58c24-128">Vergleichen Sie Ihre Punktzahl mit Organisationen wie Ihrem</span><span class="sxs-lookup"><span data-stu-id="58c24-128">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="58c24-129">Anzeigen von Verbesserungs Aktionen und Festlegen eines Aktionsplans</span><span class="sxs-lookup"><span data-stu-id="58c24-129">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="58c24-130">Initiieren von Workflows zur Untersuchung oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="58c24-130">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="58c24-131">Microsoft 365 Security Center und ServiceNow-Integration</span><span class="sxs-lookup"><span data-stu-id="58c24-131">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="58c24-132">Wie Verbesserungsmaßnahmen bewertet werden</span><span class="sxs-lookup"><span data-stu-id="58c24-132">How improvement actions are scored</span></span>

<span data-ttu-id="58c24-133">Jede Verbesserungsmaßnahme hat einen Wert von höchstens 10 Punkten.</span><span class="sxs-lookup"><span data-stu-id="58c24-133">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="58c24-134">Die meisten werden auf binäre Art bewertet – wenn Sie die Verbesserungsmaßnahme umsetzen, wie z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren –, erhalten Sie die volle Punktzahl.</span><span class="sxs-lookup"><span data-stu-id="58c24-134">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="58c24-135">Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.</span><span class="sxs-lookup"><span data-stu-id="58c24-135">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="58c24-136">Wenn beispielsweise die Verbesserungs Aktion besagt, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 50 von 100 Gesamtanzahl der Benutzer geschützt haben, erhalten Sie einen Teil der Punktzahl von 5 Punkten (50 Protected/100 total \* 10 max PTS = 5 Pkt Partial Score).</span><span class="sxs-lookup"><span data-stu-id="58c24-136">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="58c24-137">Produkte in Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="58c24-137">Products included in Secure Score</span></span>

<span data-ttu-id="58c24-138">Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP und Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="58c24-138">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="58c24-139">Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="58c24-139">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="58c24-140">Die Empfehlungen umfassen nicht alle Angriffsflächen, die jedem Produkt zugeordnet sind, sind aber ein guter Ausgangsbasis.</span><span class="sxs-lookup"><span data-stu-id="58c24-140">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="58c24-141">Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.</span><span class="sxs-lookup"><span data-stu-id="58c24-141">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="58c24-142">Standardsicherheitseinstellungen </span><span class="sxs-lookup"><span data-stu-id="58c24-142">Security defaults</span></span>

<span data-ttu-id="58c24-143">Microsoft Secure Score enthält aktualisierte Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="58c24-143">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="58c24-144">Wenn Sie Sicherheitsstandards aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungs Aktionen:</span><span class="sxs-lookup"><span data-stu-id="58c24-144">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="58c24-145">Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)</span><span class="sxs-lookup"><span data-stu-id="58c24-145">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="58c24-146">MFA für Administratorrollen erforderlich (10 Punkte)</span><span class="sxs-lookup"><span data-stu-id="58c24-146">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="58c24-147">Aktivieren einer Richtlinie zum Blockieren der Legacy Authentifizierung (7 Punkte)</span><span class="sxs-lookup"><span data-stu-id="58c24-147">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="58c24-148">Zu den Sicherheitsstandards gehören Sicherheitsfeatures, die der Verbesserungs Aktion "Anmeldungs Risiko Richtlinie" und "Benutzer Risiko Richtlinie" ähnliche Sicherheit bieten.</span><span class="sxs-lookup"><span data-stu-id="58c24-148">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="58c24-149">Anstatt diese Richtlinien zusätzlich zu den Sicherheitsstandards einzurichten, empfehlen wir, ihre Status auf "durch alternative Schadensbegrenzende Maßnahmen behoben" zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="58c24-149">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="58c24-150">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="58c24-150">Required permissions</span></span>

<span data-ttu-id="58c24-151">Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.</span><span class="sxs-lookup"><span data-stu-id="58c24-151">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="58c24-152">Rollen "Lesen und Schreiben"</span><span class="sxs-lookup"><span data-stu-id="58c24-152">Read and write roles</span></span>

<span data-ttu-id="58c24-153">Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren.</span><span class="sxs-lookup"><span data-stu-id="58c24-153">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="58c24-154">Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.</span><span class="sxs-lookup"><span data-stu-id="58c24-154">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="58c24-155">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="58c24-155">Global administrator</span></span>
* <span data-ttu-id="58c24-156">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="58c24-156">Security administrator</span></span>
* <span data-ttu-id="58c24-157">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="58c24-157">Exchange administrator</span></span>
* <span data-ttu-id="58c24-158">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="58c24-158">SharePoint administrator</span></span>
* <span data-ttu-id="58c24-159">Kontoadministrator</span><span class="sxs-lookup"><span data-stu-id="58c24-159">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="58c24-160">Schreibgeschützte Rollen</span><span class="sxs-lookup"><span data-stu-id="58c24-160">Read-only roles</span></span>

<span data-ttu-id="58c24-161">Bei schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungsmaßnahme nicht bearbeiten, sowie keine Ergebniszonen oder benutzerdefinierte Vergleiche bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="58c24-161">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="58c24-162">Helpdesk-Administrator</span><span class="sxs-lookup"><span data-stu-id="58c24-162">Helpdesk administrator</span></span>
* <span data-ttu-id="58c24-163">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="58c24-163">User administrator</span></span>
* <span data-ttu-id="58c24-164">Service-Administrator</span><span class="sxs-lookup"><span data-stu-id="58c24-164">Service administrator</span></span>
* <span data-ttu-id="58c24-165">Benutzer mit Leseberechtigung für Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="58c24-165">Security reader</span></span>
* <span data-ttu-id="58c24-166">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="58c24-166">Security operator</span></span>
* <span data-ttu-id="58c24-167">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="58c24-167">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="58c24-168">Risikobewusstsein</span><span class="sxs-lookup"><span data-stu-id="58c24-168">Risk awareness</span></span>

<span data-ttu-id="58c24-169">Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus, die auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Maßstäben basiert. Hierbei handelt es sich nicht um eine absolute Messung, wie wahrscheinlich eine Sicherheitsverletzung Ihres System oder Ihrer Daten ist.</span><span class="sxs-lookup"><span data-stu-id="58c24-169">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="58c24-170">Vielmehr stellt Sie das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die das Risiko einer Sicherheitsverletzung ausgleichen können.</span><span class="sxs-lookup"><span data-stu-id="58c24-170">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="58c24-171">Kein Onlinedienst ist vollkommen immun gegen Sicherheitsverstöße, und Sicherheitsbewertung sollte in keiner Weise als Garantie gegen Sicherheitsverstöße interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="58c24-171">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="58c24-172">Wir freuen uns über Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="58c24-172">We want to hear from you</span></span>

<span data-ttu-id="58c24-173">Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy).</span><span class="sxs-lookup"><span data-stu-id="58c24-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="58c24-174">Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="58c24-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="58c24-175">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="58c24-175">Related resources</span></span>

- [<span data-ttu-id="58c24-176">Bewerten Ihrer Sicherheitsposition</span><span class="sxs-lookup"><span data-stu-id="58c24-176">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="58c24-177">Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele</span><span class="sxs-lookup"><span data-stu-id="58c24-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="58c24-178">Was in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="58c24-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="58c24-179">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="58c24-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
