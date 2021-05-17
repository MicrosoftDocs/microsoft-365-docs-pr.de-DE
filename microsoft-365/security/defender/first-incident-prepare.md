---
title: Vorbereiten Ihrer Sicherheitslage für Ihren ersten Vorfall
description: Richten Sie die Sicherheitslage Ihres Microsoft 365-Mandanten für Ihren ersten Vorfall in Microsoft 365 Defender ein.
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
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297164"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="75154-104">Vorbereiten Ihrer Sicherheitslage für Ihren ersten Vorfall</span><span class="sxs-lookup"><span data-stu-id="75154-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="75154-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="75154-105">**Applies to:**</span></span>
- <span data-ttu-id="75154-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75154-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75154-107">Die Vorbereitung der Behandlung von Vorfällen umfasst die Einrichtung eines ausreichenden Schutzes des Netzwerks einer Organisation vor verschiedenen Arten von Sicherheitsvorfällen.</span><span class="sxs-lookup"><span data-stu-id="75154-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="75154-108">Um das Risiko von Sicherheitsvorfällen zu verringern, empfiehlt das National Institute of Standards and Technology (NIST) mehrere Sicherheitspraktiken, einschließlich Risikobewertungen, Die Sicherung der Hostsicherheit, das sichere Konfigurieren von Netzwerken und das Verhindern von Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="75154-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="75154-109">Microsoft 365 Defender kann dabei helfen, verschiedene Aspekte der Verhinderung von Vorfällen zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="75154-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="75154-110">Implementieren eines [Zero Trust-Frameworks](https://docs.microsoft.com/security/zero-trust/)</span><span class="sxs-lookup"><span data-stu-id="75154-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="75154-111">Bestimmen Ihrer Sicherheitslage durch Zuweisen einer Bewertung mit [Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="75154-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="75154-112">Verhindern von Bedrohungen durch Sicherheitsrisikobewertungen im [Bedrohungs- und Sicherheitsrisikomanagement](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="75154-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="75154-113">Grundlegendes zu den neuesten Sicherheitsbedrohungen, damit Sie sich darauf vorbereiten können</span><span class="sxs-lookup"><span data-stu-id="75154-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="75154-114">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="75154-114">Step 1.</span></span> <span data-ttu-id="75154-115">Implementieren der Nullvertrauensstellung</span><span class="sxs-lookup"><span data-stu-id="75154-115">Implement Zero Trust</span></span>

<span data-ttu-id="75154-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) ist eine integrierte Sicherheitsphilosophie und End-to-End-Strategie, die den komplexen Charakter jeder modernen Umgebung berücksichtigt, einschließlich der mobilen Mitarbeiter und der Benutzer, Geräte, Anwendungen und Daten, unabhängig davon, wo sie sich befinden.</span><span class="sxs-lookup"><span data-stu-id="75154-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="75154-117">Durch die Bereitstellung eines einzigen Fensterausschnitts zur konsistenten Verwaltung aller Endpunkterkennungen kann Microsoft 365 [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Defender Ihrem Sicherheitsteam die Implementierung der Leitprinzipien von Zero Trust erleichtern.</span><span class="sxs-lookup"><span data-stu-id="75154-117">By providing a single pane of glass to manage all endpoint detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="75154-118">Komponenten von Microsoft 365 Defender können Verstöße gegen Regeln anzeigen, die implementiert wurden, um Richtlinien für bedingten Zugriff für Zero Trust zu erstellen, indem Daten von Microsoft Defender for Endpoint (MDE) oder anderen mobilen Sicherheitsanbietern als Informationsquelle für Gerätekonformitätsrichtlinien und die Implementierung gerätebasierter Bedingter Zugriffsrichtlinien integriert werden.</span><span class="sxs-lookup"><span data-stu-id="75154-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="75154-119">Das Geräterisiko wirkt sich direkt darauf aus, auf welche Ressourcen der Benutzer dieses Geräts zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="75154-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="75154-120">Die Verweigerung des Zugriffs auf Ressourcen basierend auf bestimmten Kriterien ist das Hauptthema von Zero Trust, und Microsoft 365 Defender stellt Informationen zur Verfügung, die zum Bestimmen der Kriterien auf Vertrauensebene erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="75154-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="75154-121">Beispielsweise kann Microsoft 365 Defender die Softwareversionsebene eines Geräts über die Seite Bedrohungs- und Sicherheitsrisikoverwaltung bereitstellen, während Richtlinien für bedingten Zugriff Geräte mit veralteten oder anfälligen Versionen einschränken.</span><span class="sxs-lookup"><span data-stu-id="75154-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="75154-122">Die Automatisierung ist ein wichtiger Bestandteil der Implementierung und Aufrechterhaltung einer Zero Trust-Umgebung und reduziert gleichzeitig die Anzahl der Warnungen, die potenziell zu Vorfallreaktionsereignissen führen würden.</span><span class="sxs-lookup"><span data-stu-id="75154-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="75154-123">Komponenten von Microsoft 365 Defender können automatisiert werden, z. B. Korrekturaktionen [(als](m365d-autoir.md) Untersuchungen für einen Vorfall im Microsoft 365 Security Center bezeichnet), Benachrichtigungsaktionen und sogar das Erstellen von Supporttickets wie in [ServiceNow](https://microsoft.service-now.com/sp/).</span><span class="sxs-lookup"><span data-stu-id="75154-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="75154-124">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="75154-124">Step 2.</span></span> <span data-ttu-id="75154-125">Bestimmen der Sicherheitslage Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="75154-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="75154-126">Als Nächstes können Organisationen die [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender verwenden, um Ihre aktuelle Sicherheitslage zu ermitteln und Empfehlungen zur Verbesserung zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="75154-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="75154-127">Je höher die Bewertung ist, desto mehr Sicherheitsempfehlungen und Verbesserungsmaßnahmen wurden von der Organisation ergriffen.</span><span class="sxs-lookup"><span data-stu-id="75154-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="75154-128">Empfehlungen für die sichere Bewertung können für verschiedene Produkte verwendet werden und es Organisationen ermöglichen, ihre Ergebnisse noch weiter zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="75154-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Beispiel für Microsoft Secure Score im Microsoft Security Center":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="75154-130">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="75154-130">Step 3.</span></span> <span data-ttu-id="75154-131">Bewerten der Sicherheitsrisikorisiken In Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="75154-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="75154-132">Die Verhinderung von Vorfällen kann dazu beitragen, die Sicherheitsvorgänge zu optimieren, um sich auf wichtige und wichtige Sicherheitsvorfälle zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="75154-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="75154-133">Softwarerisiken sind häufig ein verhinderbarer Einstiegspunkt für Angriffe, die zu Datendiebstahl, Datenverlust oder Unterbrechungen des Geschäftsbetriebs führen können.</span><span class="sxs-lookup"><span data-stu-id="75154-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="75154-134">Wenn keine Angriffe im Einsatz sind, müssen Sicherheitsvorgänge bestrebt sein, ein akzeptables Maß an Sicherheitsrisiko [in](../defender-endpoint/tvm-exposure-score.md) ihrer Organisation zu erreichen und auf dem Niveau zu halten.</span><span class="sxs-lookup"><span data-stu-id="75154-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="75154-135">Um den Fortschritt des Softwarepatchings zu überprüfen, besuchen Sie die Seite Bedrohungs- und Sicherheitsrisikoverwaltung in Defender for Endpoint, auf die Sie von Microsoft 365 Defender über die Registerkarte Weitere Ressourcen **zugreifen** können. [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="75154-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Beispiel für die Seite &quot;Bedrohung und Sicherheitsanfälligkeit&quot; im Microsoft Security Center"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="75154-137">4. Verstehen neuer Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="75154-137">4. Understand emerging threats</span></span>

<span data-ttu-id="75154-138">Verwenden [Sie die Bedrohungsanalyse](threat-analytics.md) im Microsoft 365 Security Center, um mit der aktuellen Sicherheitsrisikolandschaft auf dem neuesten Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="75154-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="75154-139">Erfahrene Microsoft-Sicherheitsforscher erstellen Berichte, in denen die neuesten Cyberbedrohungen detailliert beschrieben werden, damit Sie verstehen können, wie sich diese auf Ihr Microsoft 365-Abonnement, Ihre Geräte und Ihre Benutzer auswirken können.</span><span class="sxs-lookup"><span data-stu-id="75154-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="75154-140">Diese Berichte können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="75154-140">These reports can include:</span></span>

- <span data-ttu-id="75154-141">Aktive Bedrohungsakteure und ihre Kampagnen</span><span class="sxs-lookup"><span data-stu-id="75154-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="75154-142">Beliebte und neue Angriffstechniken</span><span class="sxs-lookup"><span data-stu-id="75154-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="75154-143">Kritische Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="75154-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="75154-144">Allgemeine Angriffsoberflächen</span><span class="sxs-lookup"><span data-stu-id="75154-144">Common attack surfaces</span></span>
- <span data-ttu-id="75154-145">Verbreitete Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="75154-145">Prevalent malware</span></span>

<span data-ttu-id="75154-146">Sie können die Empfehlungen einer neuen Bedrohung implementieren, um Ihre Sicherheitslage zu stärken und ihre Angriffsfläche zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="75154-146">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="75154-147">Nehmen Sie sich Zeit in Ihrem Zeitplan, um den Abschnitt [Threat Analytics](threat-analytics.md) des Microsoft 365 Security Centers regelmäßig zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="75154-147">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="75154-148">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="75154-148">Next step</span></span>

<span data-ttu-id="75154-149">[![Schritt 1: Erfahren Sie, wie Sie Vorfälle analysieren und analysieren.](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="75154-149">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="75154-150">Erfahren Sie, [wie Sie Vorfälle triagen und analysieren.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="75154-150">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75154-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75154-151">See also</span></span>

- [<span data-ttu-id="75154-152">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="75154-152">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="75154-153">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="75154-153">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="75154-154">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="75154-154">Manage incidents</span></span>](manage-incidents.md)
