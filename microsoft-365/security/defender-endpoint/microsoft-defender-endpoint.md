---
title: Microsoft Defender für Endpunkt
description: Microsoft Defender for Endpoint ist eine Sicherheitsplattform für Unternehmensendpunkte, die bei der Verteidigung vor erweiterten beständigen Bedrohungen hilft.
keywords: Einführung in Microsoft Defender for Endpoint, Einführung in Microsoft Defender Advanced Threat Protection, Einführung in Microsoft Defender ATP, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Computerverhaltenssensor, Cloudsicherheit, Analyse, Bedrohungsintelligenz, Reduzierung der Angriffsfläche, Schutz der nächsten Generation, automatisierte Untersuchung und Behebung, Microsoft Threat Experts, Secure Score, Advanced Hunting, Microsoft Threat Protection, Cyber Threat Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 8c5d02a4d76ae7e031ad9f3af0db282cc4cb45ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187213"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="02e09-104">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="02e09-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02e09-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="02e09-105">**Applies to:**</span></span>
- [<span data-ttu-id="02e09-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="02e09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02e09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02e09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="02e09-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="02e09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="02e09-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="02e09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="02e09-110">Weitere Informationen zu Windows 10 Enterprise Edition-Features und -Funktionen finden Sie unter [Windows 10 Enterprise Edition](https://www.microsoft.com/WindowsForBusiness/buy).</span><span class="sxs-lookup"><span data-stu-id="02e09-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="02e09-111">Microsoft Defender for Endpoint ist eine Unternehmensendpunktsicherheitsplattform, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und auf sie zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="02e09-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="02e09-112">Defender for Endpoint verwendet die folgende Kombination aus Technologie, die in Windows 10 und dem robusten Clouddienst von Microsoft integrierte ist:</span><span class="sxs-lookup"><span data-stu-id="02e09-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="02e09-113">**Endpunktverhaltenssensoren:** Eingebettet in Windows 10 erfassen und verarbeiten diese Sensoren Verhaltenssignale vom Betriebssystem und senden diese Sensordaten an Ihre private, isolierte Cloudinstanz von Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="02e09-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="02e09-114">**Cloudsicherheitsanalyse:** Unter Verwendung von Big Data, Device-Learning und einzigartiger Microsoft-Optik im gesamten Windows-Ökosystem, in Enterprise-Cloud-Produkten (z. B. Office 365) und Onlineressourcen werden Verhaltenssignale in Einblicke, Erkennungen und empfohlene Antworten auf erweiterte Bedrohungen übersetzt.</span><span class="sxs-lookup"><span data-stu-id="02e09-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="02e09-115">Bedrohungsintelligenz: Generiert von Microsoft-Jägern, Sicherheitsteams und erweitert durch Bedrohungsintelligenz, die von Partnern bereitgestellt wird, ermöglicht die Bedrohungsintelligenz Defender for Endpoint, Angreifertools, -techniken und -verfahren zu identifizieren und Warnungen zu generieren, wenn sie in gesammelten Sensordaten beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="02e09-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="02e09-116">Microsoft Defender for Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="02e09-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="02e09-117"><b>Sicherheitsrisikoverwaltung & Bedrohungen</b></center></a></span><span class="sxs-lookup"><span data-stu-id="02e09-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="02e09-118"><b>Reduzierung der Angriffsfläche</b></center></a></span><span class="sxs-lookup"><span data-stu-id="02e09-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="02e09-119"><b>Schutz der nächsten Generation</b></a></center></span><span class="sxs-lookup"><span data-stu-id="02e09-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="02e09-120"><b>Endpunkterkennung und -antwort</b></a></center></span><span class="sxs-lookup"><span data-stu-id="02e09-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="02e09-121"><b>Automatisierte Untersuchung und Behebung</b></a></center></span><span class="sxs-lookup"><span data-stu-id="02e09-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="02e09-122"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="02e09-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="02e09-123">
<a href="#apis"><center><b>Zentrale Konfiguration und Verwaltung, APIs</a></span><span class="sxs-lookup"><span data-stu-id="02e09-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="02e09-124"><a href="#mtp"><center><b>Microsoft Threat Protection</a></span><span class="sxs-lookup"><span data-stu-id="02e09-124"><a href="#mtp"><center><b>Microsoft Threat Protection</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="02e09-125">Erfahren Sie mehr über die neuesten Verbesserungen in Defender for Endpoint: [Neuigkeiten in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="02e09-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="02e09-126">Microsoft Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="02e09-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="02e09-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="02e09-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="02e09-128">**[Sicherheitsrisikoverwaltung & Bedrohungen](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="02e09-129">Diese integrierte Funktion verwendet einen spielveränderungsbasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunktrisiken und Fehlkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="02e09-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="02e09-130">**[Reduzierung der Angriffsfläche](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="02e09-131">Der Satz von Funktionen zur Reduzierung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel bereit.</span><span class="sxs-lookup"><span data-stu-id="02e09-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="02e09-132">Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich die Funktionen gegen Angriffe und Diebenutzung.</span><span class="sxs-lookup"><span data-stu-id="02e09-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="02e09-133">Dieser Satz von Funktionen umfasst auch [Netzwerkschutz](network-protection.md) und [Webschutz,](web-protection-overview.md)die den Zugriff auf schädliche IP-Adressen, Domänen und URLs regeln.</span><span class="sxs-lookup"><span data-stu-id="02e09-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="02e09-134">**[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="02e09-134">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="02e09-135">Zur weiteren Verstärkung des Sicherheitsperimeters Ihres Netzwerks verwendet Microsoft Defender for Endpoint den Schutz der nächsten Generation, der alle Arten neuer Bedrohungen abfangen soll.</span><span class="sxs-lookup"><span data-stu-id="02e09-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="02e09-136">**[Endpunkterkennung und -antwort](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="02e09-137">Funktionen zur Erkennung und Reaktion von Endpunkten werden zum Erkennen, Untersuchen und Reagieren auf erweiterte Bedrohungen verwendet, die die ersten beiden Sicherheitspfeiler möglicherweise über die ersten beiden Sicherheitspfeiler hinaus haben.</span><span class="sxs-lookup"><span data-stu-id="02e09-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="02e09-138">[Die erweiterte Suche](advanced-hunting-overview.md) bietet ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Verstöße proaktiv finden und benutzerdefinierte Erkennungen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="02e09-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="02e09-139">**[Automatisierte Untersuchung und Behebung](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="02e09-140">In Verbindung mit der schnellen Reaktion auf erweiterte Angriffe bietet Microsoft Defender for Endpoint automatische Untersuchungs- und Korrekturfunktionen, mit deren Hilfe das Volumen von Warnungen in Minuten im Großen reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="02e09-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="02e09-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="02e09-142">Defender for Endpoint enthält Microsoft Secure Score for Devices, mit dem Sie den Sicherheitsstatus Ihres Unternehmensnetzwerks dynamisch bewerten, nicht geschützte Systeme identifizieren und empfohlene Maßnahmen ergreifen können, um die allgemeine Sicherheit Ihrer Organisation zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="02e09-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="02e09-143">**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="02e09-144">Der neue dienst für die Suche nach verwalteten Bedrohungen von Microsoft Defender for Endpoint bietet proaktives Aufsuchen, Priorisierung sowie zusätzliche Kontexte und Einblicke, mit denen Sicherheitsoperationscenter (Security Operation Center, SOCs) Bedrohungen schnell und präzise identifizieren und darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="02e09-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="02e09-145">Defender for Endpoint-Kunden müssen den verwalteten Dienst zur Bedrohungssuche von Microsoft Threat Experts beantragen, um proaktive Benachrichtigungen über gezielte Angriffe zu erhalten und bei Bedarf mit Experten zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="02e09-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="02e09-146">Experts on Demand ist ein Add-On-Dienst.</span><span class="sxs-lookup"><span data-stu-id="02e09-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="02e09-147">Gezielte Angriffsbenachrichtigungen werden immer einbezogen, nachdem Sie in den verwalteten Dienst für die Bedrohungssuche von Microsoft Threat Experts aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="02e09-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="02e09-148">Wenn Sie noch nicht registriert sind und ihre Vorteile nutzen möchten, wechseln Sie zu <b>Einstellungen</b> > <b>Allgemeine</b> > <b>erweiterte</b> Funktionen Microsoft > <b>Threat Experts,</b> um sich zu bewerben.</span><span class="sxs-lookup"><span data-stu-id="02e09-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="02e09-149">Sobald sie akzeptiert wurden, erhalten Sie die Vorteile von Benachrichtigungen über gezielte Angriffe und starten eine 90-tägige Testversion von Experten bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="02e09-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="02e09-150">Wenden Sie sich an Ihren Microsoft-Vertreter, um ein vollständiges Experts on Demand-Abonnement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="02e09-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="02e09-151">**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="02e09-152">Integrieren Sie Microsoft Defender for Endpoint in Ihre vorhandenen Workflows.</span><span class="sxs-lookup"><span data-stu-id="02e09-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="02e09-153">**[Integration in Microsoft-Lösungen](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="02e09-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="02e09-154">Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden, darunter:</span><span class="sxs-lookup"><span data-stu-id="02e09-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="02e09-155">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="02e09-155">Azure Security Center</span></span>
- <span data-ttu-id="02e09-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="02e09-156">Azure Sentinel</span></span>
- <span data-ttu-id="02e09-157">Intune</span><span class="sxs-lookup"><span data-stu-id="02e09-157">Intune</span></span>
- <span data-ttu-id="02e09-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02e09-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="02e09-159">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="02e09-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="02e09-160">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="02e09-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="02e09-161">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02e09-161">Skype for Business</span></span>

<span data-ttu-id="02e09-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="02e09-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="02e09-163">Mit Microsoft 365 Defender bilden Defender for Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ über Endpunkte, Identitäten, E-Mails und Anwendungen hinweg integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="02e09-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="02e09-164">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="02e09-164">Related topic</span></span>
[<span data-ttu-id="02e09-165">Microsoft Defender for Endpoint hilft beim Erkennen anspruchsvoller Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="02e09-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)