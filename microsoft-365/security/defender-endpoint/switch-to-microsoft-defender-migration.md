---
title: Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint
description: Wechseln Sie zu Microsoft Defender for Endpoint. In diesem Artikel finden Sie eine Übersicht.
keywords: migration, windows defender advanced endpoint protection, for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2c6029a1aada8f5f5fb27723c868f28c3de6f8aa
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218652"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="da5f0-105">Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da5f0-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="da5f0-106">Wenn Sie planen, von einer Nicht-Microsoft-Lösung für den Endpunktschutz zu Microsoft Defender for Endpoint (Defender for [Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) zu wechseln, sind Sie an der richtigen Stelle.</span><span class="sxs-lookup"><span data-stu-id="da5f0-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="da5f0-107">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="da5f0-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Übersicht über die Migration zu Defender for Endpoint":::

<span data-ttu-id="da5f0-109">Wenn Sie zu Defender for Endpoint wechseln, beginnen Sie mit Ihrer Nicht-Microsoft-Lösung im aktiven Modus, konfigurieren Defender für Endpoint im passiven Modus, onboard zu Defender für Endpoint, und legen Sie dann Defender für Endpoint auf den aktiven Modus und entfernen Sie die Nicht-Microsoft-Lösung.</span><span class="sxs-lookup"><span data-stu-id="da5f0-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="da5f0-110">Wenn Sie derzeit McAfee Endpoint Security (McAfee) verwenden, lesen Sie Migrieren von [McAfee zu Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span><span class="sxs-lookup"><span data-stu-id="da5f0-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="da5f0-111">Wenn Sie derzeit Symantec Endpoint Protection (Symantec) verwenden, lesen [Sie Migrieren von Symantec zu Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span><span class="sxs-lookup"><span data-stu-id="da5f0-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="da5f0-112">Der Migrationsprozess</span><span class="sxs-lookup"><span data-stu-id="da5f0-112">The migration process</span></span>

<span data-ttu-id="da5f0-113">Wenn Sie zu Microsoft Defender for Endpoint wechseln, führen Sie einen Prozess durch, der in drei Phasen unterteilt werden kann, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="da5f0-113">When you switch to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![Migrationsphasen – Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="da5f0-115">Phase</span><span class="sxs-lookup"><span data-stu-id="da5f0-115">Phase</span></span> |<span data-ttu-id="da5f0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5f0-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="da5f0-117">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="da5f0-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="da5f0-118">Während [der **Vorbereitungsphase**](switch-to-microsoft-defender-prepare.md)aktualisieren Sie die Geräte Ihrer Organisation, erhalten Microsoft Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf das Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="da5f0-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="da5f0-119">Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Microsoft Defender for Endpoint zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="da5f0-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="da5f0-120">Einrichten von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da5f0-120">Set up Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="da5f0-121">Während [  ](switch-to-microsoft-defender-setup.md)der Setupphase aktivieren Sie Microsoft Defender Antivirus und stellen sicher, dass es sich im passiven Modus befindet, und Sie konfigurieren Einstellungen & Ausschlüssen für Microsoft Defender Antivirus, Microsoft Defender for Endpoint und Ihre vorhandene Endpunktschutzlösung.</span><span class="sxs-lookup"><span data-stu-id="da5f0-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and make sure it's in passive mode, and you configure settings & exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and your existing endpoint protection solution.</span></span> <span data-ttu-id="da5f0-122">Außerdem erstellen Sie Gerätegruppen, Sammlungen und Organisationseinheiten.</span><span class="sxs-lookup"><span data-stu-id="da5f0-122">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="da5f0-123">Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="da5f0-123">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="da5f0-124">Onboarding bei Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da5f0-124">Onboard to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="da5f0-125">Während [der **Onboardphase**](switch-to-microsoft-defender-onboard.md)integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint und überprüfen, ob diese Geräte mit Microsoft Defender for Endpoint kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="da5f0-125">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="da5f0-126">Zuletzt deinstallieren Sie Ihre vorhandene Endpunktschutzlösung, und stellen Sie sicher, dass sich der Schutz über Microsoft Defender Antivirus & Microsoft Defender for Endpoint im aktiven Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="da5f0-126">Last, you uninstall your existing endpoint protection solution and make sure that protection through Microsoft Defender Antivirus & Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="da5f0-127">Was ist in Microsoft Defender for Endpoint enthalten?</span><span class="sxs-lookup"><span data-stu-id="da5f0-127">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="da5f0-128">In diesem Migrationshandbuch konzentrieren wir uns [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) auf [Schutz-](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) und Endpunkterkennungs- und Reaktionsfunktionen der nächsten Generation als Ausgangspunkt für den Wechsel zu Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="da5f0-128">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="da5f0-129">Microsoft Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz.</span><span class="sxs-lookup"><span data-stu-id="da5f0-129">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="da5f0-130">Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion.</span><span class="sxs-lookup"><span data-stu-id="da5f0-130">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="da5f0-131">In der folgenden Tabelle sind die Features und Funktionen in Microsoft Defender for Endpoint zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="da5f0-131">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="da5f0-132">Feature/Funktion</span><span class="sxs-lookup"><span data-stu-id="da5f0-132">Feature/Capability</span></span> | <span data-ttu-id="da5f0-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5f0-133">Description</span></span> |
|---|---|
| [<span data-ttu-id="da5f0-134">Sicherheitsrisikoverwaltung & Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="da5f0-134">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="da5f0-135">Funktionen & zur Verwaltung von Sicherheitslücken helfen, Schwachstellen auf Ihren Endpunkten (z. B. Geräten) zu identifizieren, zu bewerten und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="da5f0-135">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="da5f0-136">Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="da5f0-136">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="da5f0-137">Regeln zur Reduzierung der Angriffsfläche schützen die Geräte und Anwendungen Ihrer Organisation vor Cyberangriffen und Angriffen.</span><span class="sxs-lookup"><span data-stu-id="da5f0-137">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="da5f0-138">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="da5f0-138">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="da5f0-139">Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="da5f0-139">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="da5f0-140">Endpunkterkennung und -antwort</span><span class="sxs-lookup"><span data-stu-id="da5f0-140">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="da5f0-141">Erkennungs- und Reaktionsfunktionen für Endpunkte erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Verstöße.</span><span class="sxs-lookup"><span data-stu-id="da5f0-141">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="da5f0-142">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="da5f0-142">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="da5f0-143">Erweiterte Suchesfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden.</span><span class="sxs-lookup"><span data-stu-id="da5f0-143">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="da5f0-144">Verhaltensblockierung und -eindämmung</span><span class="sxs-lookup"><span data-stu-id="da5f0-144">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="da5f0-145">Verhaltensblockierungs- und -eindämmungsfunktionen helfen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="da5f0-145">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="da5f0-146">Automatisierte Untersuchung und Behebung</span><span class="sxs-lookup"><span data-stu-id="da5f0-146">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="da5f0-147">Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben.</span><span class="sxs-lookup"><span data-stu-id="da5f0-147">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="da5f0-148">[Threat Hunting Service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span><span class="sxs-lookup"><span data-stu-id="da5f0-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="da5f0-149">Bedrohungssuchen bieten Sicherheitsteams Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden.</span><span class="sxs-lookup"><span data-stu-id="da5f0-149">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="da5f0-150">**Möchten Sie mehr erfahren? Weitere [Informationen finden Sie unter Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span><span class="sxs-lookup"><span data-stu-id="da5f0-150">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="da5f0-151">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="da5f0-151">Next step</span></span>

- <span data-ttu-id="da5f0-152">Fahren Sie mit [Prepare for your migration fort.](switch-to-microsoft-defender-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="da5f0-152">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>