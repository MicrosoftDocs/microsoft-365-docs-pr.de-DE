---
title: Vorbereiten des Sicherheitsstatus für Ihren ersten Vorfall
description: Richten Sie den Sicherheitsstatus Ihres Microsoft 365 Mandanten für Ihren ersten Vorfall in Microsoft 365 Defender ein.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fcdce7f5a41c23dfe33eb75ef15b579ac12c8742
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194937"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="f26ae-104">Vorbereiten des Sicherheitsstatus für Ihren ersten Vorfall</span><span class="sxs-lookup"><span data-stu-id="f26ae-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f26ae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f26ae-105">**Applies to:**</span></span>
- <span data-ttu-id="f26ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f26ae-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f26ae-107">Die Vorbereitung auf die Behandlung von Sicherheitsvorfällen umfasst das Einrichten eines ausreichenden Schutzes des Netzwerks einer Organisation vor verschiedenen Arten von Sicherheitsvorfällen.</span><span class="sxs-lookup"><span data-stu-id="f26ae-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="f26ae-108">Um das Risiko von Sicherheitsvorfällen zu verringern, empfiehlt das National Institute of Standards and Technology (NIST) verschiedene Sicherheitspraktiken, einschließlich Risikobewertungen, Härtung der Hostsicherheit, sichere Konfiguration von Netzwerken und Verhinderung von Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="f26ae-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="f26ae-109">Microsoft 365 Defender können ihnen dabei helfen, verschiedene Aspekte der Vorfallsverhütung zu behandeln:</span><span class="sxs-lookup"><span data-stu-id="f26ae-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="f26ae-110">Implementieren eines [Zero Trust-Frameworks](/security/zero-trust/)</span><span class="sxs-lookup"><span data-stu-id="f26ae-110">Implementing a [Zero Trust](/security/zero-trust/) framework</span></span>
- <span data-ttu-id="f26ae-111">Bestimmen Ihres Sicherheitsstatus durch Zuweisen einer Bewertung mit [der Microsoft-Sicherheitsbewertung](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="f26ae-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="f26ae-112">Verhindern von Bedrohungen durch Sicherheitsrisikobewertungen im [Bedrohungs- und Sicherheitsrisikomanagement](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="f26ae-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="f26ae-113">Grundlegendes zu den neuesten Sicherheitsbedrohungen, damit Sie sich darauf vorbereiten können</span><span class="sxs-lookup"><span data-stu-id="f26ae-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="f26ae-114">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="f26ae-114">Step 1.</span></span> <span data-ttu-id="f26ae-115">Implementieren von Zero Trust</span><span class="sxs-lookup"><span data-stu-id="f26ae-115">Implement Zero Trust</span></span>

<span data-ttu-id="f26ae-116">[Zero Trust](/security/zero-trust/) ist eine integrierte Sicherheits-Philosophie und End-to-End-Strategie, die den komplexen Charakter jeder modernen Umgebung berücksichtigt, einschließlich der mobilen Mitarbeiter und der Benutzer, Geräte, Anwendungen und Daten, unabhängig davon, wo sie sich befinden.</span><span class="sxs-lookup"><span data-stu-id="f26ae-116">[Zero Trust](/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="f26ae-117">Durch die Bereitstellung eines einzigen Fensterausschnitts zur konsistenten Verwaltung aller Erkennungen können Microsoft 365 Defender es Ihrem Sicherheitsteam erleichtern, die [Leitprinzipien](/security/zero-trust/#guiding-principles-of-zero-trust) von Zero Trust zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f26ae-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="f26ae-118">Komponenten von Microsoft 365 Defender können Verstöße gegen Regeln anzeigen, die implementiert wurden, um Richtlinien für bedingten Zugriff für Zero Trust einzurichten, indem Daten von Microsoft Defender für Endpunkt oder anderen mobilen Sicherheitsanbietern als Informationsquelle für Gerätekompatibilitätsrichtlinien und die Implementierung von gerätebasierten Richtlinien für bedingten Zugriff integriert werden.</span><span class="sxs-lookup"><span data-stu-id="f26ae-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="f26ae-119">Das Geräterisiko wirkt sich direkt darauf aus, auf welche Ressourcen der Benutzer dieses Geräts zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f26ae-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="f26ae-120">Die Verweigerung des Zugriffs auf Ressourcen basierend auf bestimmten Kriterien ist das Hauptdesign von Zero Trust, und Microsoft 365 Defender liefert Informationen, die erforderlich sind, um die Kriterien für die Vertrauensebene zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f26ae-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="f26ae-121">Beispielsweise können Microsoft 365 Defender die Softwareversionsebene eines Geräts über die Seite "Bedrohungs- und Sicherheitsrisikoverwaltung" bereitstellen, während Richtlinien für bedingten Zugriff Geräte mit veralteten oder anfälligen Versionen einschränken.</span><span class="sxs-lookup"><span data-stu-id="f26ae-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="f26ae-122">Automatisierung ist ein wichtiger Bestandteil der Implementierung und Pflege einer Zero Trust-Umgebung, während gleichzeitig die Anzahl der Warnungen reduziert wird, die potenziell zu Ereignissen bei der Reaktion auf Vorfälle (Incident Response, IR) führen würden.</span><span class="sxs-lookup"><span data-stu-id="f26ae-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="f26ae-123">Komponenten von Microsoft 365 Defender können automatisiert werden, z. B. [Wartungsaktionen](m365d-autoir.md) (bekannt als Untersuchungen für einen Vorfall im Microsoft 365 Security Center), Benachrichtigungsaktionen und sogar die Erstellung von Supporttickets wie in [ServiceNow.](https://microsoft.service-now.com/sp/)</span><span class="sxs-lookup"><span data-stu-id="f26ae-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="f26ae-124">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="f26ae-124">Step 2.</span></span> <span data-ttu-id="f26ae-125">Bestimmen des Sicherheitsstatus Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f26ae-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="f26ae-126">Als Nächstes können Organisationen die [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) in Microsoft 365 Defender verwenden, um Ihren aktuellen Sicherheitsstatus zu bestimmen und Empfehlungen zur Verbesserung zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f26ae-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="f26ae-127">Je höher die Bewertung ist, desto mehr Sicherheitsempfehlungen und Verbesserungsmaßnahmen wurden von der Organisation durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f26ae-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="f26ae-128">Empfehlungen für die Sicherheitsbewertung können über verschiedene Produkte hinweg angewendet werden und ermöglichen Es Organisationen, ihre Bewertungen noch weiter zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f26ae-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Beispiel für die Microsoft-Sicherheitsbewertung im Microsoft Security Center":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="f26ae-130">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="f26ae-130">Step 3.</span></span> <span data-ttu-id="f26ae-131">Bewerten der Sicherheitsrisiken Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f26ae-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="f26ae-132">Die Verhinderung von Vorfällen kann dazu beitragen, die Sicherheitsvorgänge zu optimieren, um sich auf laufende kritische und wichtige Sicherheitsvorfälle zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="f26ae-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="f26ae-133">Softwarerisiken sind häufig ein verhinderbarer Einstiegspunkt für Angriffe, die zu Datendiebstahl, Datenverlust oder Betriebsunterbrechungen führen können.</span><span class="sxs-lookup"><span data-stu-id="f26ae-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="f26ae-134">Wenn keine Angriffe ausgeführt werden, müssen Sicherheitsvorgänge versuchen, ein akzeptables Maß an [Sicherheitsrisiken](../defender-endpoint/tvm-exposure-score.md) in ihrer Organisation zu erreichen und aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="f26ae-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="f26ae-135">Um den Fortschritt des Softwarepatchings zu überprüfen, besuchen Sie die Seite ["Bedrohungs- und Sicherheitsrisikoverwaltung"](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) in Defender für Endpunkt, auf die Sie über Microsoft 365 Defender über die Registerkarte **"Weitere Ressourcen"** zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f26ae-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Beispiel für die Seite &quot;Bedrohung und Sicherheitsanfälligkeit&quot; im Microsoft Security Center"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="f26ae-137">4. Verstehen neuer Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="f26ae-137">4. Understand emerging threats</span></span>

<span data-ttu-id="f26ae-138">Verwenden Sie [die Bedrohungsanalyse](threat-analytics.md) im Microsoft 365 Security Center, um mit der aktuellen Sicherheitsbedrohungslandschaft auf dem neuesten Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="f26ae-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="f26ae-139">Erfahrene Microsoft-Sicherheitsexperten erstellen Berichte, die die neuesten Cyberbedrohungen detailliert beschreiben, damit Sie verstehen können, wie sie sich auf Ihr Microsoft 365 Abonnement, Geräte und Benutzer auswirken können.</span><span class="sxs-lookup"><span data-stu-id="f26ae-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="f26ae-140">Diese Berichte können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="f26ae-140">These reports can include:</span></span>

- <span data-ttu-id="f26ae-141">Aktive Bedrohungsteilnehmer und ihre Kampagnen</span><span class="sxs-lookup"><span data-stu-id="f26ae-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="f26ae-142">Beliebte und neue Angriffstechniken</span><span class="sxs-lookup"><span data-stu-id="f26ae-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="f26ae-143">Kritische Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="f26ae-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="f26ae-144">Allgemeine Angriffsflächen</span><span class="sxs-lookup"><span data-stu-id="f26ae-144">Common attack surfaces</span></span>
- <span data-ttu-id="f26ae-145">Weit verbreitete Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="f26ae-145">Prevalent malware</span></span>

<span data-ttu-id="f26ae-146">Die Bedrohungsanalyse untersucht auch Ihre Konfiguration und Warnungen, um zu ermitteln, wie gefährdet Sie sind und ob aktive Warnungen für einen Bericht anwendbar sind.</span><span class="sxs-lookup"><span data-stu-id="f26ae-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="f26ae-147">Sie können die Empfehlungen einer neuen Bedrohung implementieren, um Ihren Sicherheitsstatus zu stärken und den Angriffsbereich zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="f26ae-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="f26ae-148">Nehmen Sie sich Zeit in Ihrem Zeitplan, um den Abschnitt ["Bedrohungsanalyse"](threat-analytics.md) im Microsoft 365 Security Center regelmäßig zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f26ae-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="f26ae-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f26ae-149">Next step</span></span>

<span data-ttu-id="f26ae-150">[![Schritt 1: Erfahren Sie, wie Sie Vorfälle selektieren und analysieren](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="f26ae-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="f26ae-151">Erfahren Sie, wie Sie [Vorfälle selektieren und analysieren.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="f26ae-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f26ae-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f26ae-152">See also</span></span>

- [<span data-ttu-id="f26ae-153">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="f26ae-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f26ae-154">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f26ae-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f26ae-155">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f26ae-155">Manage incidents</span></span>](manage-incidents.md)
