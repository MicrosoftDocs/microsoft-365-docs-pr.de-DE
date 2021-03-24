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
# <a name="threat-protection"></a>Bedrohungsschutz
[Microsoft Defender für Endpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. Defender for Endpoint schützt Endpunkte vor Cyberbedrohungen, erkennt erweiterte Angriffe und Datenschutzverletzungen, automatisiert Sicherheitsvorfälle und verbessert die Sicherheitslage.

> [!TIP]
> Ermöglichen Sie Ihren Benutzern den problemlosen Zugriff auf Clouddienste und lokale Anwendungen und ermöglichen Sie moderne Verwaltungsfunktionen für alle Geräte. Weitere Informationen finden Sie unter [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/). 

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Sicherheitsrisikoverwaltung & Bedrohungen</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Reduzierung der Angriffsfläche</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Schutz der nächsten Generation</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Endpunkterkennung und -antwort</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Automatisierte Untersuchung und Behebung</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft Threat Experts</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Zentrale Konfiguration und Verwaltung, APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Sicherheitsrisikoverwaltung & Bedrohungen](next-gen-threat-and-vuln-mgt.md)**<br>
Diese integrierte Funktion verwendet einen spielveränderungsbasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunktrisiken und Fehlkonfigurationen.

- [Übersicht & Zur Verwaltung von Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Erste Schritte](tvm-prerequisites.md)
- [Zugreifen auf Ihre Sicherheitslage](tvm-dashboard-insights.md)
- [Verbessern Sie Ihre Sicherheitslage und verringern Sie das Risiko](tvm-security-recommendation.md)
- [Verstehen von Sicherheitsrisiken auf Ihren Geräten](tvm-software-inventory.md)

<a name="asr"></a>

**[Reduzierung der Angriffsfläche](overview-attack-surface-reduction.md)**<br>
Der Satz von Funktionen zur Reduzierung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel bereit. Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich diese Funktionen gegen Angriffe und Nutzung.

- [Hardwarebasierte Isolation](overview-hardware-based-isolation.md)
- [Anwendungssteuerung](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Gerätesteuerung](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Exploit-Schutz](exploit-protection.md)
- [Netzwerkschutz,](network-protection.md) [Webschutz](web-protection-overview.md)
- [Kontrollierter Ordnerzugriff](controlled-folders.md)
- [Netzwerkfirewall](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)

<a name="ngp"></a>

**[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Zur weiteren Verstärkung des Sicherheitsperimeters Ihres Netzwerks verwendet Microsoft Defender for Endpoint den Schutz der nächsten Generation, der alle Arten neuer Bedrohungen abfangen soll.

- [Verhaltensüberwachung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Cloudbasierter Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Maschinelles Lernen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL-Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Automatisierter Sandkastendienst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Endpunkterkennung und -antwort](overview-endpoint-detection-response.md)**<br>
Funktionen zur Erkennung und Reaktion von Endpunkten werden zum Erkennen, Untersuchen und Reagieren auf Angriffsversuche und aktive Sicherheitsverletzungen verwendet. Mit der erweiterten Suche verfügen Sie über ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Verstöße proaktiv finden und benutzerdefinierte Erkennungen erstellen können.

- [Benachrichtigungen](alerts-queue.md)
- [Historische Endpunktdaten](investigate-machines.md#timeline)
- [Reaktions orchestrierung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Forensische Sammlung](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Bedrohungsintelligenz](threat-indicator-concepts.md)
- [Erweiterter Detonations- und Analysedienst](respond-file-alerts.md#deep-analysis)
- [Erweiterte Suche](advanced-hunting-overview.md)
    - [Benutzerdefinierte Erkennungen](overview-custom-detections.md)

<a name="ai"></a>

**[Automatisierte Untersuchung und Behebung](automated-investigations.md)**<br>
Neben der schnellen Reaktion auf erweiterte Angriffe bietet Microsoft Defender for Endpoint automatische Untersuchungs- und Korrekturfunktionen, mit deren Hilfe das Volumen von Warnungen in Minuten im Umfang reduziert werden kann.

- [Automatisierte Untersuchung und Behebung](automated-investigations.md)
- [Anzeigen von Details und Ergebnissen von automatischen Untersuchungen](auto-investigation-action-center.md)
- [Anzeigen und Genehmigen von Korrekturaktionen](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**<br>
Der neue Dienst für die Suche nach verwalteten Bedrohungen von Microsoft Defender for Endpoint bietet proaktive Suche, Priorisierung sowie zusätzliche Kontexte und Einblicke. Microsoft Threat Experts unterstützt Security Operation Center (SOCs) außerdem, Bedrohungen schnell und präzise zu identifizieren und darauf zu reagieren.

- [Benachrichtigung über gezielte Angriffe](microsoft-threat-experts.md)
- [Experten bei Bedarf](microsoft-threat-experts.md)
- [Konfigurieren Ihres verwalteten Microsoft 365 Defender-Suchediensts](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**<br>
Integrieren Sie Microsoft Defender for Endpoint in Ihre vorhandenen Workflows.
- [Onboarding](onboard-configure.md)
- [API- und SIEM-Integration](configure-siem.md)
- [Verfügbar gemachte APIs](apis-intro.md)
- [Rollenbasierte Zugriffssteuerung (RBAC)](rbac.md)
- [Berichterstellung und Trends](threat-protection-reports.md)

<a name="integration"></a>
**[Integration in Microsoft-Lösungen](threat-protection-integration.md)** <br>
 Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden, darunter:
- Intune
- Microsoft Defender für Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype for Business
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.
