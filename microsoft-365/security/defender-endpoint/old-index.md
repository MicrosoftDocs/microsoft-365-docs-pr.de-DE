---
title: Threat Protection (Windows 10)
description: Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion.
keywords: Bedrohungsschutz, Microsoft Defender Advanced Threat Protection, Reduzierung der Angriffsfläche, Schutz der nächsten Generation, Endpunkterkennung und -reaktion, automatisierte Untersuchung und Reaktion, Microsoft-Bedrohungsexperten, Microsoft Secure Score für Geräte, erweiterte Suche, Suche nach Cyberbedrohungen, Schutz vor Webbedrohungen
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061165"
---
# <a name="threat-protection"></a><span data-ttu-id="2ac73-104">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="2ac73-104">Threat Protection</span></span>
<span data-ttu-id="2ac73-105">[Microsoft Defender für Endpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion.</span><span class="sxs-lookup"><span data-stu-id="2ac73-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="2ac73-106">Defender for Endpoint schützt Endpunkte vor Cyberbedrohungen, erkennt erweiterte Angriffe und Datenschutzverletzungen, automatisiert Sicherheitsvorfälle und verbessert die Sicherheitslage.</span><span class="sxs-lookup"><span data-stu-id="2ac73-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="2ac73-107">Ermöglichen Sie Ihren Benutzern den problemlosen Zugriff auf Clouddienste und lokale Anwendungen und ermöglichen Sie moderne Verwaltungsfunktionen für alle Geräte.</span><span class="sxs-lookup"><span data-stu-id="2ac73-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="2ac73-108">Weitere Informationen finden Sie unter [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span><span class="sxs-lookup"><span data-stu-id="2ac73-108">For more information, see [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="2ac73-109">Microsoft Defender for Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="2ac73-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="2ac73-110"><b>Sicherheitsrisikoverwaltung & Bedrohungen</b></center></a></span><span class="sxs-lookup"><span data-stu-id="2ac73-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="2ac73-111"><b>Reduzierung der Angriffsfläche</b></center></a></span><span class="sxs-lookup"><span data-stu-id="2ac73-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="2ac73-112"><b>Schutz der nächsten Generation</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ac73-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="2ac73-113"><b>Endpunkterkennung und -antwort</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ac73-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="2ac73-114"><b>Automatisierte Untersuchung und Behebung</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ac73-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="2ac73-115"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ac73-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="2ac73-116">
<a href="#apis"><center><b>Zentrale Konfiguration und Verwaltung, APIs</a></span><span class="sxs-lookup"><span data-stu-id="2ac73-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="2ac73-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="2ac73-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="2ac73-118">**[Sicherheitsrisikoverwaltung & Bedrohungen](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="2ac73-119">Diese integrierte Funktion verwendet einen spielveränderungsbasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunktrisiken und Fehlkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="2ac73-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="2ac73-120">Übersicht & Zur Verwaltung von Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="2ac73-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2ac73-121">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="2ac73-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="2ac73-122">Zugreifen auf Ihre Sicherheitslage</span><span class="sxs-lookup"><span data-stu-id="2ac73-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="2ac73-123">Verbessern Sie Ihre Sicherheitslage und verringern Sie das Risiko</span><span class="sxs-lookup"><span data-stu-id="2ac73-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="2ac73-124">Verstehen von Sicherheitsrisiken auf Ihren Geräten</span><span class="sxs-lookup"><span data-stu-id="2ac73-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="2ac73-125">**[Reduzierung der Angriffsfläche](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="2ac73-126">Der Satz von Funktionen zur Reduzierung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel bereit.</span><span class="sxs-lookup"><span data-stu-id="2ac73-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="2ac73-127">Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich diese Funktionen gegen Angriffe und Nutzung.</span><span class="sxs-lookup"><span data-stu-id="2ac73-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="2ac73-128">Hardwarebasierte Isolation</span><span class="sxs-lookup"><span data-stu-id="2ac73-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="2ac73-129">Anwendungssteuerung</span><span class="sxs-lookup"><span data-stu-id="2ac73-129">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="2ac73-130">Gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="2ac73-130">Device control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="2ac73-131">Exploit-Schutz</span><span class="sxs-lookup"><span data-stu-id="2ac73-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="2ac73-132">[Netzwerkschutz,](network-protection.md) [Webschutz](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2ac73-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="2ac73-133">Kontrollierter Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="2ac73-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="2ac73-134">Netzwerkfirewall</span><span class="sxs-lookup"><span data-stu-id="2ac73-134">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="2ac73-135">Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2ac73-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="2ac73-136">**[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-136">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="2ac73-137">Zur weiteren Verstärkung des Sicherheitsperimeters Ihres Netzwerks verwendet Microsoft Defender for Endpoint den Schutz der nächsten Generation, der alle Arten neuer Bedrohungen abfangen soll.</span><span class="sxs-lookup"><span data-stu-id="2ac73-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="2ac73-138">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="2ac73-138">Behavior monitoring</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="2ac73-139">Cloudbasierter Schutz</span><span class="sxs-lookup"><span data-stu-id="2ac73-139">Cloud-based protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="2ac73-140">Maschinelles Lernen</span><span class="sxs-lookup"><span data-stu-id="2ac73-140">Machine learning</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="2ac73-141">URL-Schutz</span><span class="sxs-lookup"><span data-stu-id="2ac73-141">URL Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="2ac73-142">Automatisierter Sandkastendienst</span><span class="sxs-lookup"><span data-stu-id="2ac73-142">Automated sandbox service</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="2ac73-143">**[Endpunkterkennung und -antwort](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="2ac73-144">Funktionen zur Erkennung und Reaktion von Endpunkten werden zum Erkennen, Untersuchen und Reagieren auf Angriffsversuche und aktive Sicherheitsverletzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ac73-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="2ac73-145">Mit der erweiterten Suche verfügen Sie über ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Verstöße proaktiv finden und benutzerdefinierte Erkennungen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2ac73-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="2ac73-146">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="2ac73-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="2ac73-147">Historische Endpunktdaten</span><span class="sxs-lookup"><span data-stu-id="2ac73-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="2ac73-148">Reaktions orchestrierung</span><span class="sxs-lookup"><span data-stu-id="2ac73-148">Response orchestration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="2ac73-149">Forensische Sammlung</span><span class="sxs-lookup"><span data-stu-id="2ac73-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="2ac73-150">Bedrohungsintelligenz</span><span class="sxs-lookup"><span data-stu-id="2ac73-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="2ac73-151">Erweiterter Detonations- und Analysedienst</span><span class="sxs-lookup"><span data-stu-id="2ac73-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="2ac73-152">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2ac73-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="2ac73-153">Benutzerdefinierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="2ac73-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="2ac73-154">**[Automatisierte Untersuchung und Behebung](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="2ac73-155">Neben der schnellen Reaktion auf erweiterte Angriffe bietet Microsoft Defender for Endpoint automatische Untersuchungs- und Korrekturfunktionen, mit deren Hilfe das Volumen von Warnungen in Minuten im Umfang reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ac73-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="2ac73-156">Automatisierte Untersuchung und Behebung</span><span class="sxs-lookup"><span data-stu-id="2ac73-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="2ac73-157">Anzeigen von Details und Ergebnissen von automatischen Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="2ac73-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="2ac73-158">Anzeigen und Genehmigen von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="2ac73-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="2ac73-159">**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="2ac73-160">Der neue Dienst für die Suche nach verwalteten Bedrohungen von Microsoft Defender for Endpoint bietet proaktive Suche, Priorisierung sowie zusätzliche Kontexte und Einblicke.</span><span class="sxs-lookup"><span data-stu-id="2ac73-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="2ac73-161">Microsoft Threat Experts unterstützt Security Operation Center (SOCs) außerdem, Bedrohungen schnell und präzise zu identifizieren und darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2ac73-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="2ac73-162">Benachrichtigung über gezielte Angriffe</span><span class="sxs-lookup"><span data-stu-id="2ac73-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="2ac73-163">Experten bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="2ac73-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="2ac73-164">Konfigurieren Ihres verwalteten Microsoft 365 Defender-Suchediensts</span><span class="sxs-lookup"><span data-stu-id="2ac73-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="2ac73-165">**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="2ac73-166">Integrieren Sie Microsoft Defender for Endpoint in Ihre vorhandenen Workflows.</span><span class="sxs-lookup"><span data-stu-id="2ac73-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="2ac73-167">Onboarding</span><span class="sxs-lookup"><span data-stu-id="2ac73-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="2ac73-168">API- und SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="2ac73-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="2ac73-169">Verfügbar gemachte APIs</span><span class="sxs-lookup"><span data-stu-id="2ac73-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="2ac73-170">Rollenbasierte Zugriffssteuerung (RBAC)</span><span class="sxs-lookup"><span data-stu-id="2ac73-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="2ac73-171">Berichterstellung und Trends</span><span class="sxs-lookup"><span data-stu-id="2ac73-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="2ac73-172">**[Integration in Microsoft-Lösungen](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="2ac73-173">Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden, darunter:</span><span class="sxs-lookup"><span data-stu-id="2ac73-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="2ac73-174">Intune</span><span class="sxs-lookup"><span data-stu-id="2ac73-174">Intune</span></span>
- <span data-ttu-id="2ac73-175">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="2ac73-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="2ac73-176">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ac73-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="2ac73-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="2ac73-177">Azure Defender</span></span>
- <span data-ttu-id="2ac73-178">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2ac73-178">Skype for Business</span></span>
- <span data-ttu-id="2ac73-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ac73-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="2ac73-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="2ac73-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="2ac73-181">Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2ac73-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
