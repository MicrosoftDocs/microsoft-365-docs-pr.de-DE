---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitsposition verbessern und welche Sicherheitsadministratoren erwarten können.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Improvement Actions
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682571"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="71260-104">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="71260-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71260-105">Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="71260-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="71260-106">Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="71260-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="71260-107">Wenn Sie die Secure Score-Empfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen.</span><span class="sxs-lookup"><span data-stu-id="71260-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="71260-108">Von einem zentralisierten Dashboard im Microsoft 365 Security Center aus können Organisationen die Sicherheit Ihrer Microsoft 365-Identitäten,-Apps und-Geräte überwachen und daran arbeiten.</span><span class="sxs-lookup"><span data-stu-id="71260-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="71260-109">Sicherheitsbewertung hilft Organisationen auf diese Arten:</span><span class="sxs-lookup"><span data-stu-id="71260-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="71260-110">Berichtet über den aktuellen Sicherheitsstatus der Organisation.</span><span class="sxs-lookup"><span data-stu-id="71260-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="71260-111">Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="71260-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="71260-112">Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="71260-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="71260-113">Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="71260-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="71260-114">Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="71260-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="71260-116">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="71260-116">How it works</span></span>

<span data-ttu-id="71260-117">Für die folgenden Aktionen werden Punkte angegeben:</span><span class="sxs-lookup"><span data-stu-id="71260-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="71260-118">Konfigurieren von empfohlenen Sicherheitsfeatures</span><span class="sxs-lookup"><span data-stu-id="71260-118">Configuring recommended security features</span></span>
- <span data-ttu-id="71260-119">Durchführen von sicherheitsbezogenen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="71260-119">Performing security-related tasks</span></span>
- <span data-ttu-id="71260-120">Beheben der Verbesserungs Aktion mit einer Anwendung oder Software eines Drittanbieters oder einer alternativen Minderung</span><span class="sxs-lookup"><span data-stu-id="71260-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="71260-121">Einige Verbesserungs Aktionen geben nur dann Punkte an, wenn Sie vollständig abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="71260-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="71260-122">Einige geben partielle Punkte an, wenn Sie für einige Geräte oder Benutzer abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="71260-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="71260-123">Wenn Sie eine der Verbesserungs Aktionen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="71260-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="71260-124">Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Ihnen Empfehlungen für diese Produkte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71260-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="71260-125">Wir zeigen Ihnen den vollständigen Umfang möglicher Verbesserungen für ein Produkt, unabhängig von Lizenzedition, Abonnement oder Plan.</span><span class="sxs-lookup"><span data-stu-id="71260-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="71260-126">Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern.</span><span class="sxs-lookup"><span data-stu-id="71260-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="71260-127">Ihre absolute Sicherheitsposition, dargestellt durch Secure Score, bleibt gleich, unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt.</span><span class="sxs-lookup"><span data-stu-id="71260-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="71260-128">Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="71260-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="71260-129">Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="71260-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="71260-130">Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="71260-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="71260-131">Schlüsselszenarien</span><span class="sxs-lookup"><span data-stu-id="71260-131">Key scenarios</span></span>

- [<span data-ttu-id="71260-132">Überprüfen der aktuellen Bewertung</span><span class="sxs-lookup"><span data-stu-id="71260-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="71260-133">Vergleichen Sie Ihre Punktzahl mit Organisationen wie Ihrem</span><span class="sxs-lookup"><span data-stu-id="71260-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="71260-134">Anzeigen von Verbesserungs Aktionen und Festlegen eines Aktionsplans</span><span class="sxs-lookup"><span data-stu-id="71260-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="71260-135">Initiieren von Workflows zur Untersuchung oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="71260-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="71260-136">Microsoft 365 Security Center und ServiceNow-Integration</span><span class="sxs-lookup"><span data-stu-id="71260-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="71260-137">Wie Verbesserungsmaßnahmen bewertet werden</span><span class="sxs-lookup"><span data-stu-id="71260-137">How improvement actions are scored</span></span>

<span data-ttu-id="71260-138">Jede Verbesserungs Aktion ist 10 oder mehr Punkte Wert, und die meisten werden auf binäre Weise bewertet.</span><span class="sxs-lookup"><span data-stu-id="71260-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="71260-139">Wenn Sie die Verbesserungs Aktion implementieren, wie Sie eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100% der Punkte.</span><span class="sxs-lookup"><span data-stu-id="71260-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="71260-140">Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.</span><span class="sxs-lookup"><span data-stu-id="71260-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="71260-141">Beispielsweise besagt eine Verbesserungs Aktion, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen.</span><span class="sxs-lookup"><span data-stu-id="71260-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="71260-142">Sie haben nur 50 von 100 Gesamtanzahl der Benutzer geschützt, sodass Sie einen Teil der Punktzahl von 5 Punkten erhalten (50 Protected/100 total \* 10 max PTS = 5 Pkt.).</span><span class="sxs-lookup"><span data-stu-id="71260-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="71260-143">Produkte in Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="71260-143">Products included in Secure Score</span></span>

<span data-ttu-id="71260-144">Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity und Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="71260-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="71260-145">Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="71260-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="71260-146">Die Empfehlungen decken nicht alle Angriffsflächen ab, die jedem Produkt zugeordnet sind, sind jedoch ein guter Ausgangswert.</span><span class="sxs-lookup"><span data-stu-id="71260-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="71260-147">Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.</span><span class="sxs-lookup"><span data-stu-id="71260-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="71260-148">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="71260-148">Security defaults</span></span>

<span data-ttu-id="71260-149">Microsoft Secure Score enthält aktualisierte Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="71260-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="71260-150">Wenn Sie Sicherheitsstandards aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungs Aktionen:</span><span class="sxs-lookup"><span data-stu-id="71260-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="71260-151">Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)</span><span class="sxs-lookup"><span data-stu-id="71260-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="71260-152">MFA für Administratorrollen erforderlich (10 Punkte)</span><span class="sxs-lookup"><span data-stu-id="71260-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="71260-153">Aktivieren einer Richtlinie zum Blockieren der Legacy Authentifizierung (7 Punkte)</span><span class="sxs-lookup"><span data-stu-id="71260-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="71260-154">Zu den Sicherheitsstandards gehören Sicherheitsfeatures, die der Verbesserungs Aktion "Anmeldungs Risiko Richtlinie" und "Benutzer Risiko Richtlinie" ähnliche Sicherheit bieten.</span><span class="sxs-lookup"><span data-stu-id="71260-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="71260-155">Anstatt diese Richtlinien zusätzlich zu den Sicherheitsstandards einzurichten, empfehlen wir, ihre Status auf "durch alternative Schadensbegrenzende Maßnahmen behoben" zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="71260-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="71260-156">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="71260-156">Required permissions</span></span>

<span data-ttu-id="71260-157">Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.</span><span class="sxs-lookup"><span data-stu-id="71260-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="71260-158">Rollen "Lesen und Schreiben"</span><span class="sxs-lookup"><span data-stu-id="71260-158">Read and write roles</span></span>

<span data-ttu-id="71260-159">Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren.</span><span class="sxs-lookup"><span data-stu-id="71260-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="71260-160">Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71260-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="71260-161">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="71260-161">Global administrator</span></span>
* <span data-ttu-id="71260-162">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="71260-162">Security administrator</span></span>
* <span data-ttu-id="71260-163">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="71260-163">Exchange administrator</span></span>
* <span data-ttu-id="71260-164">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="71260-164">SharePoint administrator</span></span>
* <span data-ttu-id="71260-165">Kontoadministrator</span><span class="sxs-lookup"><span data-stu-id="71260-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="71260-166">Schreibgeschützte Rollen</span><span class="sxs-lookup"><span data-stu-id="71260-166">Read-only roles</span></span>

<span data-ttu-id="71260-167">Mit schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungs Aktion nicht bearbeiten, Bewertungs Zonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="71260-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="71260-168">Helpdesk-Administrator</span><span class="sxs-lookup"><span data-stu-id="71260-168">Helpdesk administrator</span></span>
* <span data-ttu-id="71260-169">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="71260-169">User administrator</span></span>
* <span data-ttu-id="71260-170">Service-Administrator</span><span class="sxs-lookup"><span data-stu-id="71260-170">Service administrator</span></span>
* <span data-ttu-id="71260-171">Benutzer mit Leseberechtigung für Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="71260-171">Security reader</span></span>
* <span data-ttu-id="71260-172">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="71260-172">Security operator</span></span>
* <span data-ttu-id="71260-173">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="71260-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="71260-174">Risikobewusstsein</span><span class="sxs-lookup"><span data-stu-id="71260-174">Risk awareness</span></span>

<span data-ttu-id="71260-175">Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen.</span><span class="sxs-lookup"><span data-stu-id="71260-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="71260-176">Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="71260-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="71260-177">Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, um das Risiko von Verstößen auszugleichen.</span><span class="sxs-lookup"><span data-stu-id="71260-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="71260-178">Kein Onlinedienst ist vollständig immun gegen Sicherheitsverletzungen, und Secure Score sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="71260-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="71260-179">Wir freuen uns über Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="71260-179">We want to hear from you</span></span>

<span data-ttu-id="71260-180">Wenn Sie Probleme haben, lassen Sie es uns wissen, indem Sie in der [Sicherheits-, Datenschutz-& Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="71260-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="71260-181">Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="71260-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="71260-182">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="71260-182">Related resources</span></span>

- [<span data-ttu-id="71260-183">Zugreifen auf Ihren Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="71260-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="71260-184">Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele</span><span class="sxs-lookup"><span data-stu-id="71260-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="71260-185">Was in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="71260-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="71260-186">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="71260-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
