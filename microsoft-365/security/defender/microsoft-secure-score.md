---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitslage verbessern und welche Sicherheitsadministratoren erwarten können.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, microsoft 365 Security Center, Verbesserungsmaßnahmen
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
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245377"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="60454-104">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="60454-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="60454-105">Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="60454-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="60454-106">Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="60454-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="60454-107">Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen.</span><span class="sxs-lookup"><span data-stu-id="60454-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="60454-108">Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365, Apps und Geräte überwachen und arbeiten.</span><span class="sxs-lookup"><span data-stu-id="60454-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="60454-109">Sicherheitsbewertung hilft Organisationen auf diese Arten:</span><span class="sxs-lookup"><span data-stu-id="60454-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="60454-110">Berichtet über den aktuellen Sicherheitsstatus der Organisation.</span><span class="sxs-lookup"><span data-stu-id="60454-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="60454-111">Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="60454-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="60454-112">Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="60454-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="60454-113">Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="60454-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="60454-114">Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="60454-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="60454-116">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="60454-116">How it works</span></span>

<span data-ttu-id="60454-117">Sie erhalten Punkte für die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="60454-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="60454-118">Konfigurieren empfohlener Sicherheitsfeatures</span><span class="sxs-lookup"><span data-stu-id="60454-118">Configuring recommended security features</span></span>
- <span data-ttu-id="60454-119">Ausführen sicherheitsbezogener Aufgaben</span><span class="sxs-lookup"><span data-stu-id="60454-119">Doing security-related tasks</span></span>
- <span data-ttu-id="60454-120">Adressieren der Verbesserungsaktion mit einer Drittanbieteranwendung oder -software oder einer alternativen Gegenmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="60454-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="60454-121">Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="60454-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="60454-122">Einige geben Teilpunkte, wenn sie für einige Geräte oder Benutzer abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="60454-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="60454-123">Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="60454-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="60454-124">Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Empfehlungen für diese Produkte erhalten.</span><span class="sxs-lookup"><span data-stu-id="60454-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="60454-125">Wir zeigen Ihnen den vollständigen Satz möglicher Verbesserungen für ein Produkt, unabhängig von der Lizenz edition, dem Abonnement oder dem Plan.</span><span class="sxs-lookup"><span data-stu-id="60454-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="60454-126">Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Bewertung verbessern.</span><span class="sxs-lookup"><span data-stu-id="60454-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="60454-127">Ihre absolute Sicherheitshaltung, dargestellt durch Secure Score, bleibt unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt, gleich.</span><span class="sxs-lookup"><span data-stu-id="60454-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="60454-128">Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="60454-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="60454-129">Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="60454-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="60454-130">Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="60454-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="60454-131">Schlüsselszenarien</span><span class="sxs-lookup"><span data-stu-id="60454-131">Key scenarios</span></span>

- [<span data-ttu-id="60454-132">Überprüfen Ihrer aktuellen Bewertung</span><span class="sxs-lookup"><span data-stu-id="60454-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="60454-133">Vergleichen Ihrer Bewertung mit Organisationen wie Ihrer</span><span class="sxs-lookup"><span data-stu-id="60454-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="60454-134">Anzeigen von Verbesserungsmaßnahmen und Festlegen eines Aktionsplans</span><span class="sxs-lookup"><span data-stu-id="60454-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="60454-135">Initiieren von Arbeitsflüssen zur Untersuchung oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="60454-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="60454-136">Wie Verbesserungsmaßnahmen bewertet werden</span><span class="sxs-lookup"><span data-stu-id="60454-136">How improvement actions are scored</span></span>

<span data-ttu-id="60454-137">Jede Verbesserungsaktion hat einen Wert von 10 Punkten oder weniger, und die meisten werden auf binäre Weise erzielt.</span><span class="sxs-lookup"><span data-stu-id="60454-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="60454-138">Wenn Sie die Verbesserungsaktion implementieren, z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100 % der Punkte.</span><span class="sxs-lookup"><span data-stu-id="60454-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="60454-139">Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.</span><span class="sxs-lookup"><span data-stu-id="60454-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="60454-140">Eine Verbesserungsaktion beispielsweise besagt, dass Sie 10 Punkte erhalten, indem Sie alle Benutzer mit mehrstufiger Authentifizierung schützen.</span><span class="sxs-lookup"><span data-stu-id="60454-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="60454-141">Sie haben nur 50 von insgesamt 100 Benutzern geschützt, sodass Sie eine Teilpunktzahl von 5 Punkten erhalten (50 geschützte /100 insgesamt \* 10 max. Pts = 5 Pts).</span><span class="sxs-lookup"><span data-stu-id="60454-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="60454-142">Produkte in Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="60454-142">Products included in Secure Score</span></span>

<span data-ttu-id="60454-143">Derzeit gibt es Empfehlungen für die folgenden Produkte:</span><span class="sxs-lookup"><span data-stu-id="60454-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="60454-144">Microsoft 365 (einschließlich Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="60454-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="60454-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="60454-145">Azure Active Directory</span></span>
- <span data-ttu-id="60454-146">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="60454-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="60454-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="60454-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="60454-148">Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="60454-148">Cloud App Security</span></span>
- <span data-ttu-id="60454-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60454-149">Microsoft Teams</span></span>

<span data-ttu-id="60454-150">Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="60454-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="60454-151">Die Empfehlungen umfassen nicht alle Angriffsflächen, die mit jedem Produkt verknüpft sind, aber sie sind eine gute Basis.</span><span class="sxs-lookup"><span data-stu-id="60454-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="60454-152">Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.</span><span class="sxs-lookup"><span data-stu-id="60454-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="60454-153">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="60454-153">Security defaults</span></span>

<span data-ttu-id="60454-154">Microsoft Secure Score hat verbesserungsaktionen aktualisiert, um Sicherheitseinstellungen [in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)zu unterstützen, die es ihnen erleichtern, Ihre Organisation mit vordefinierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="60454-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="60454-155">Wenn Sie Sicherheitseinstellungen aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungsmaßnahmen:</span><span class="sxs-lookup"><span data-stu-id="60454-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="60454-156">Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)</span><span class="sxs-lookup"><span data-stu-id="60454-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="60454-157">MFA für Administrative Rollen erforderlich (10 Punkte)</span><span class="sxs-lookup"><span data-stu-id="60454-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="60454-158">Aktivieren der Richtlinie zum Blockieren der Legacyauthentifizierung (7 Punkte)</span><span class="sxs-lookup"><span data-stu-id="60454-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="60454-159">Sicherheitseinstellungen umfassen Sicherheitsfeatures, die ähnliche Sicherheit wie die Verbesserungsmaßnahmen "Anmelderisikorichtlinie" und "Benutzerrisikorichtlinie" bieten.</span><span class="sxs-lookup"><span data-stu-id="60454-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="60454-160">Anstatt diese Richtlinien über die Sicherheitseinstellungen hinaus zu erstellen, wird empfohlen, ihre Status auf "Durch alternative Gegenmaßnahmen aufgelöst" zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60454-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="60454-161">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="60454-161">Required permissions</span></span>

<span data-ttu-id="60454-162">Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.</span><span class="sxs-lookup"><span data-stu-id="60454-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="60454-163">Rollen "Lesen und Schreiben"</span><span class="sxs-lookup"><span data-stu-id="60454-163">Read and write roles</span></span>

<span data-ttu-id="60454-164">Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren.</span><span class="sxs-lookup"><span data-stu-id="60454-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="60454-165">Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.</span><span class="sxs-lookup"><span data-stu-id="60454-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="60454-166">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="60454-166">Global administrator</span></span>
* <span data-ttu-id="60454-167">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="60454-167">Security administrator</span></span>
* <span data-ttu-id="60454-168">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="60454-168">Exchange administrator</span></span>
* <span data-ttu-id="60454-169">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="60454-169">SharePoint administrator</span></span>
* <span data-ttu-id="60454-170">Kontoadministrator</span><span class="sxs-lookup"><span data-stu-id="60454-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="60454-171">Schreibgeschützte Rollen</span><span class="sxs-lookup"><span data-stu-id="60454-171">Read-only roles</span></span>

<span data-ttu-id="60454-172">Mit schreibgeschützten Zugriffen können Sie status oder Notizen für eine Verbesserungsaktion, Bewertungszonen oder benutzerdefinierte Vergleiche nicht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="60454-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="60454-173">Helpdesk-Administrator</span><span class="sxs-lookup"><span data-stu-id="60454-173">Helpdesk administrator</span></span>
* <span data-ttu-id="60454-174">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="60454-174">User administrator</span></span>
* <span data-ttu-id="60454-175">Service-Administrator</span><span class="sxs-lookup"><span data-stu-id="60454-175">Service administrator</span></span>
* <span data-ttu-id="60454-176">Benutzer mit Leseberechtigung für Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="60454-176">Security reader</span></span>
* <span data-ttu-id="60454-177">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="60454-177">Security operator</span></span>
* <span data-ttu-id="60454-178">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="60454-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="60454-179">Risikobewusstsein</span><span class="sxs-lookup"><span data-stu-id="60454-179">Risk awareness</span></span>

<span data-ttu-id="60454-180">Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitslage basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen.</span><span class="sxs-lookup"><span data-stu-id="60454-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="60454-181">Es handelt sich nicht um eine absolute Maßeinheit für die Wahrscheinlichkeit, dass Ihr System oder Ihre Daten verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="60454-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="60454-182">Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung übernommen haben, um das Risiko einer Verletzung zu kompensieren.</span><span class="sxs-lookup"><span data-stu-id="60454-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="60454-183">Kein Onlinedienst ist immun gegen Sicherheitsverletzungen, und die Bewertung der Sicherheit sollte nicht als Garantie gegen Sicherheitsverletzungen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="60454-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="60454-184">Wir freuen uns über Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="60454-184">We want to hear from you</span></span>

<span data-ttu-id="60454-185">Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der [Community für Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="60454-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="60454-186">Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="60454-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="60454-187">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="60454-187">Related resources</span></span>

- [<span data-ttu-id="60454-188">Zugreifen auf Ihren Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="60454-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="60454-189">Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen</span><span class="sxs-lookup"><span data-stu-id="60454-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="60454-190">Was in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="60454-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="60454-191">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60454-191">What's new</span></span>](microsoft-secure-score-whats-new.md)