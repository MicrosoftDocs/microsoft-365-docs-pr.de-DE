---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt die Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, wie Sie Ihren Sicherheitsstatus verbessern und was Sicherheitsadministratoren erwarten können.
keywords: Microsoft-Sicherheitsbewertung, Sicherheitsbewertung, Office 365-Sicherheitsbewertung, Microsoft-Sicherheitsbewertung, Microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: 1b03c2671939a3e8e3011b78b8f1484ef02979ea
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930187"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="02e82-104">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="02e82-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="02e82-105">Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="02e82-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="02e82-106">Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="02e82-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="02e82-107">Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen.</span><span class="sxs-lookup"><span data-stu-id="02e82-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="02e82-108">Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365 Identitäten, Apps und Geräte überwachen und daran arbeiten.</span><span class="sxs-lookup"><span data-stu-id="02e82-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="02e82-109">Sicherheitsbewertung hilft Organisationen auf diese Arten:</span><span class="sxs-lookup"><span data-stu-id="02e82-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="02e82-110">Berichtet über den aktuellen Sicherheitsstatus der Organisation.</span><span class="sxs-lookup"><span data-stu-id="02e82-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="02e82-111">Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="02e82-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="02e82-112">Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="02e82-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="02e82-113">Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="02e82-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="02e82-114">Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="02e82-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="02e82-116">So funktioniert's</span><span class="sxs-lookup"><span data-stu-id="02e82-116">How it works</span></span>

<span data-ttu-id="02e82-117">Sie erhalten Punkte für die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="02e82-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="02e82-118">Konfigurieren empfohlener Sicherheitsfeatures</span><span class="sxs-lookup"><span data-stu-id="02e82-118">Configuring recommended security features</span></span>
- <span data-ttu-id="02e82-119">Ausführen sicherheitsrelevanter Aufgaben</span><span class="sxs-lookup"><span data-stu-id="02e82-119">Doing security-related tasks</span></span>
- <span data-ttu-id="02e82-120">Behandeln der Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software oder einer alternativen Gegenmaßnahme</span><span class="sxs-lookup"><span data-stu-id="02e82-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="02e82-121">Einige Verbesserungsmaßnahmen liefern nur Punkte, wenn sie vollständig abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="02e82-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="02e82-122">Einige geben Teilpunkte zurück, wenn sie für einige Geräte oder Benutzer abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="02e82-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="02e82-123">Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="02e82-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="02e82-124">Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Empfehlungen für diese Produkte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02e82-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="02e82-125">Wir zeigen Ihnen den vollständigen Satz möglicher Verbesserungen für ein Produkt, unabhängig von der Lizenzversion, dem Abonnement oder dem Plan.</span><span class="sxs-lookup"><span data-stu-id="02e82-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="02e82-126">Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Bewertung verbessern.</span><span class="sxs-lookup"><span data-stu-id="02e82-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="02e82-127">Ihr absoluter Sicherheitsstatus, der durch die Sicherheitsbewertung dargestellt wird, bleibt gleich, unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt.</span><span class="sxs-lookup"><span data-stu-id="02e82-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="02e82-128">Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="02e82-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="02e82-129">Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="02e82-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="02e82-130">Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="02e82-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="02e82-131">Schlüsselszenarien</span><span class="sxs-lookup"><span data-stu-id="02e82-131">Key scenarios</span></span>

- [<span data-ttu-id="02e82-132">Überprüfen Des aktuellen Bewertungsergebnisses</span><span class="sxs-lookup"><span data-stu-id="02e82-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="02e82-133">Vergleichen Sie Ihre Bewertung mit Organisationen wie Ihrer</span><span class="sxs-lookup"><span data-stu-id="02e82-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="02e82-134">Anzeigen von Verbesserungsmaßnahmen und Festlegen eines Aktionsplanes</span><span class="sxs-lookup"><span data-stu-id="02e82-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="02e82-135">Initiieren von Arbeitsflüssen zur Untersuchung oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="02e82-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="02e82-136">Wie Verbesserungsmaßnahmen bewertet werden</span><span class="sxs-lookup"><span data-stu-id="02e82-136">How improvement actions are scored</span></span>

<span data-ttu-id="02e82-137">Jede Verbesserungsmaßnahme ist mindestens 10 Punkte wert, und die meisten werden binär bewertet.</span><span class="sxs-lookup"><span data-stu-id="02e82-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="02e82-138">Wenn Sie die Verbesserungsmaßnahme implementieren, z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100 % der Punkte.</span><span class="sxs-lookup"><span data-stu-id="02e82-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="02e82-139">Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.</span><span class="sxs-lookup"><span data-stu-id="02e82-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="02e82-140">Eine Verbesserungsmaßnahme gibt beispielsweise an, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen.</span><span class="sxs-lookup"><span data-stu-id="02e82-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="02e82-141">Sie haben nur 50 von insgesamt 100 Benutzern geschützt, sodass Sie eine Partielle Bewertung von 5 Punkten erhalten (50 geschützte / 100 insgesamt \* 10 maximale Pts = 5 Pts).</span><span class="sxs-lookup"><span data-stu-id="02e82-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="02e82-142">Produkte in Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="02e82-142">Products included in Secure Score</span></span>

<span data-ttu-id="02e82-143">Derzeit gibt es Empfehlungen für die folgenden Produkte:</span><span class="sxs-lookup"><span data-stu-id="02e82-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="02e82-144">Microsoft 365 (einschließlich Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="02e82-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="02e82-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="02e82-145">Azure Active Directory</span></span>
- <span data-ttu-id="02e82-146">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="02e82-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="02e82-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="02e82-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="02e82-148">Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="02e82-148">Cloud App Security</span></span>
- <span data-ttu-id="02e82-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02e82-149">Microsoft Teams</span></span>

<span data-ttu-id="02e82-150">Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="02e82-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="02e82-151">Die Empfehlungen umfassen nicht alle Angriffsflächen, die mit jedem Produkt verbunden sind, aber sie sind eine gute Basislinie.</span><span class="sxs-lookup"><span data-stu-id="02e82-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="02e82-152">Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.</span><span class="sxs-lookup"><span data-stu-id="02e82-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="02e82-153">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="02e82-153">Security defaults</span></span>

<span data-ttu-id="02e82-154">Die Microsoft-Sicherheitsbewertung hat Verbesserungsmaßnahmen aktualisiert, um [Sicherheitsstandards in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)zu unterstützen, wodurch es einfacher ist, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="02e82-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="02e82-155">Wenn Sie die Sicherheitsstandards aktivieren, erhalten Sie alle Punkte für die folgenden Verbesserungsmaßnahmen:</span><span class="sxs-lookup"><span data-stu-id="02e82-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="02e82-156">Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für den sicheren Zugriff abschließen können (9 Punkt)</span><span class="sxs-lookup"><span data-stu-id="02e82-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="02e82-157">MFA für Administratorrollen erforderlich (10 Punkte)</span><span class="sxs-lookup"><span data-stu-id="02e82-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="02e82-158">Richtlinie zum Blockieren der Legacyauthentifizierung aktivieren (7 Punkte)</span><span class="sxs-lookup"><span data-stu-id="02e82-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="02e82-159">Zu den Sicherheitsstandards gehören Sicherheitsfeatures, die ähnliche Sicherheit wie die Verbesserungsmaßnahmen "Anmelderisikorichtlinie" und "Benutzerrisikorichtlinie" bieten.</span><span class="sxs-lookup"><span data-stu-id="02e82-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="02e82-160">Anstatt diese Richtlinien über die Sicherheitsstandards hinaus einzurichten, empfehlen wir, deren Status auf "Gelöst durch alternative Gegenmaßnahmen" zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="02e82-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="02e82-161">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="02e82-161">Required permissions</span></span>

<span data-ttu-id="02e82-162">Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.</span><span class="sxs-lookup"><span data-stu-id="02e82-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="02e82-163">Rollen "Lesen und Schreiben"</span><span class="sxs-lookup"><span data-stu-id="02e82-163">Read and write roles</span></span>

<span data-ttu-id="02e82-164">Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren.</span><span class="sxs-lookup"><span data-stu-id="02e82-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="02e82-165">Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.</span><span class="sxs-lookup"><span data-stu-id="02e82-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="02e82-166">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="02e82-166">Global administrator</span></span>
* <span data-ttu-id="02e82-167">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="02e82-167">Security administrator</span></span>
* <span data-ttu-id="02e82-168">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="02e82-168">Exchange administrator</span></span>
* <span data-ttu-id="02e82-169">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="02e82-169">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="02e82-170">Schreibgeschützte Rollen</span><span class="sxs-lookup"><span data-stu-id="02e82-170">Read-only roles</span></span>

<span data-ttu-id="02e82-171">Mit schreibgeschütztem Zugriff können Sie status oder Notizen für eine Verbesserungsmaßnahme nicht bearbeiten, keine Bewertungszonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="02e82-171">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="02e82-172">Helpdesk-Administrator</span><span class="sxs-lookup"><span data-stu-id="02e82-172">Helpdesk administrator</span></span>
* <span data-ttu-id="02e82-173">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="02e82-173">User administrator</span></span>
* <span data-ttu-id="02e82-174">Dienstsupportadministrator</span><span class="sxs-lookup"><span data-stu-id="02e82-174">Service support administrator</span></span>
* <span data-ttu-id="02e82-175">Benutzer mit Leseberechtigung für Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="02e82-175">Security reader</span></span>
* <span data-ttu-id="02e82-176">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="02e82-176">Security operator</span></span>
* <span data-ttu-id="02e82-177">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="02e82-177">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="02e82-178">Risikobewusstsein</span><span class="sxs-lookup"><span data-stu-id="02e82-178">Risk awareness</span></span>

<span data-ttu-id="02e82-179">Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Messungen.</span><span class="sxs-lookup"><span data-stu-id="02e82-179">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="02e82-180">Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System- oder Datenverstoß ist.</span><span class="sxs-lookup"><span data-stu-id="02e82-180">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="02e82-181">Vielmehr stellt es das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die dazu beitragen können, das Risiko von Sicherheitsverletzungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="02e82-181">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="02e82-182">Kein Onlinedienst ist gegen Sicherheitsverstöße immun, und die Sicherheitsbewertung sollte in keiner Weise als Garantie gegen Sicherheitsverletzungen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="02e82-182">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="02e82-183">Wir freuen uns über Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="02e82-183">We want to hear from you</span></span>

<span data-ttu-id="02e82-184">Wenn Sie Probleme haben, teilen Sie uns dies durch Veröffentlichung in der [Community für Sicherheit, Datenschutz & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) mit.</span><span class="sxs-lookup"><span data-stu-id="02e82-184">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="02e82-185">Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="02e82-185">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="02e82-186">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="02e82-186">Related resources</span></span>

- [<span data-ttu-id="02e82-187">Zugreifen auf Ihren Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="02e82-187">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="02e82-188">Nachverfolgen des Microsoft-Verlaufs der Sicherheitsbewertung und Erreichen der Ziele</span><span class="sxs-lookup"><span data-stu-id="02e82-188">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="02e82-189">Was in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="02e82-189">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="02e82-190">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="02e82-190">What's new</span></span>](microsoft-secure-score-whats-new.md)
